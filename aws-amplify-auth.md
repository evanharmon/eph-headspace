# AWS AMPLIFY AUTH

## Summary

Notes on using aws amplify auth sdk's, cli, etc

## Resources

[AWS Blog Cypress Auth Test](https://aws.amazon.com/blogs/mobile/running-end-to-end-cypress-tests-for-your-fullstack-ci-cd-deployment-with-amplify-console/)
[React Router Amplify Auth](https://www.rockyourcode.com/custom-react-hook-use-aws-amplify-auth/)
[Docs for JS](https://aws-amplify.github.io/docs/js/authentication)
[Android Setup Google OAuth2 AWS](https://www.linkedin.com/learning/building-android-apps-with-aws/set-up-user-sign-in-with-google?u=2240169)
[iOS Setup Google OAuth2 AWS](https://www.linkedin.com/learning/building-ios-apps-with-aws-mobile/add-google-login?u=2240169)

## Web App Sign In With Google

```javascript
Auth.federatedSignIn({ provider: 'Google' })
```

## Authentication Type

The valid configuration values for `aws_appsync_authenticationType` are:

- 'API_KEY'
- 'AWS_IAM'
- 'OPENID_CONNECT'
- 'AMAZON_COGNITO_USER_POOLS'

## GraphQL

[Multi-Auth Setup](https://aws-amplify.github.io/docs/js/api#multi-auth)

have to customize graphQL API Call. `graphqlOperation` can no longer be used
as it only supportes two argument objects representing `query` and `variables`

```javascript
// Creating a post is restricted to IAM
const createdTodo = await API.graphql({
  query: queries.createTodo,
  variables: { input: todoDetails },
  authMode: 'AMAZON_COGNITO_USER_POOLS',
})
```

## Sign Out Error

missing redirect_uri
check for mispellings on AWS console, cognito user pools, `Callback URLs` and
`Sign out URLs`

## Mobile Oauth2

`federatedSignIn` methods use SDK's from google / facebook that interact internally on the phone.
They are NOT web views. See linkedin Videos above in Resources

## User

### Get Current Authenticated User

```javascript
const data = await Auth.currentAuthenticatedUser()
```

### Get Cognito User Groups From Token

returns array of groups

```javascript
const groups = user.signInUserSession.accessToken.payload['cognito:groups']
```

### Get Cognito Sub ID From Token

`Auth.currentSession()` works as well

```javascript
const data = await Auth.currentAuthenticatedUser()
const sub = data.signInUserSession.accessToken.payload['sub']
```
