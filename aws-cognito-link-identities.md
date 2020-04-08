# AWS COGNITO LINK IDENTITIES

## Summary

Notes on linking and managing multiple accounts / identities for a user in
Cognito. Example being a user / password account and a google identity

## Resources

- [admin-link-provider-for-user CLI](https://docs.aws.amazon.com/cli/latest/reference/cognito-idp/admin-link-provider-for-user.html)
- [AWS FORUMS](https://forums.aws.amazon.com/thread.jspa?threadID=261470)

### Example CLI Call To Link Identity

Link a Cognito User / Password account with a Google identity. Must be done
on sign up trigger BEFORE google identity gets written to Cognito User Pools

cli-input.json

```javascript
{
  "UserPoolId": "us-east-1_aaaaaaaaa",
  "DestinationUser": {
    "ProviderName": "Cognito",
    "ProviderAttributeValue": "aaaaaaaa-aaaa-aaaa-aaaa-aaaaaaaaaaaa"
  },
  "SourceUser": {
    "ProviderName": "Google",
    "ProviderAttributeName": "Cognito_Subject",
    "ProviderAttributeValue": "111111111111111111111"
  }
}
```

### Remove Linked Identity From User / Password Account

Use the cli to delete identities in the `identities []` array in the aws
console. User / Password account will still be able to log in and perform a new
third party auth association again.

Google:

```console
aws cognito-idp admin-disable-provider-for-user \
  --user-pool-id us-east-1_aaaaaaaaa \
  --user "ProviderName=Google,ProviderAttributeName=Cognito_Subject,ProviderAttributeValue=Google_111111111111111111111"
```

### Example Code Google Linking

- [Github](https://github.com/cumulous/backend/blob/1a1438e167ebebeaa5e1477636d9b2cf8ed4c267/src/cognito.ts#L364-L388)

The userName from google that looks like `GOOGLE_1234` has to be stripped of the
prefix. The call to `adminLinkProviderForUser` must only contain the un-prefixed key

Typescript:

```typescript
export const preSignUp = (
  newUser: SignUpUserEvent,
  context: any,
  callback: Callback
) => {
  Promise.resolve()
    .then(() => {
      if (newUser.request.userAttributes.email_verified === 'false') {
        throw new ApiError(`email_verified = false for ${newUser.userName}`)
      }
      if (newUser.triggerSource === 'PreSignUp_ExternalProvider') {
        return getUserByAttribute(
          'email',
          newUser.request.userAttributes.email
        ).then(existingUser => {
          if (
            existingUser.Enabled &&
            existingUser.UserStatus === 'CONFIRMED' &&
            getUserAttribute(existingUser.Attributes, 'email_verified') ===
              'true'
          ) {
            return linkUsers(newUser.userName, existingUser.Username)
          } else {
            log.error(stringify(existingUser))
            throw new ApiError(`invalid state for ${existingUser.Username}`)
          }
        })
      }
    })
    .then(() => callback(null, newUser))
    .catch(err => {
      log.error(stringify([newUser, err]))
      callback('User signup is disabled')
    })
}
const linkUsers = (externalUsername: string, internalUsername: string) => {
  return cognito
    .adminLinkProviderForUser({
      UserPoolId: process.env[envNames.userPoolId],
      SourceUser: {
        ProviderName: externalUsername.split('_')[0],
        ProviderAttributeName: 'Cognito_Subject',
        ProviderAttributeValue: externalUsername.split('_')[1],
      },
      DestinationUser: {
        ProviderName: 'Cognito',
        ProviderAttributeValue: internalUsername,
      },
    })
    .promise()
}
```
