# AWS SDK JAVASCRIPT COGNITO IDP

## Summary

Notes on working with the javascript aws sdk and cognito user pools

## Resources

- [Docs](https://docs.aws.amazon.com/AWSJavaScriptSDK/latest/AWS/CognitoIdentityServiceProvider.html)
- [Lambda Trigger Event Shape](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-identity-pools-working-with-aws-lambda-triggers.html#cognito-user-pools-lambda-trigger-event-parameter-shared)
- [Username Already Exists](https://stackoverflow.com/questions/47815161/cognito-auth-flow-fails-with-already-found-an-entry-for-username-facebook-10155)

## Instanciate Client

```javascript
import AWS from 'aws-sdk'
const cognitoIdp = new AWS.CognitoIdentityServiceProvider()
```

## Snippets

### Get All Usersnames Via Pagination

Can be adjusted for other User attributes

```javascript
async function getAllUsernames({ UserPoolId, Limit }) {
  const AWS = require('aws-sdk')
  const cognitoIdp = new AWS.CognitoIdentityServiceProvider()
  const { createWriteStream } = require('fs')

  const wstream = createWriteStream('data.json', { flags: 'w+' })
  const params = {
    UserPoolId,
    Limit,
  }
  try {
    while (true) {
      const res = await cognitoIdp.listUsers(params).promise()
      const usernames = res.Users.map((i) => i.Username)
      wstream.write(`${JSON.stringify(usernames)}\n`) // Newline JSON
      if (undefined === res.PaginationToken) {
        break
      } else {
        params.PaginationToken = res.PaginationToken
      }
    }
  } catch (e) {
    console.error(e)
  } finally {
    wstream.end()
  }
}
```

### Get All User IDs in Group

```javascript
async function getAllUserIdsInGroup({
  UserPoolId,
  GroupName,
  Limit,
  filename = 'data.json',
}) {
  const AWS = require('aws-sdk')
  const cognitoIdp = new AWS.CognitoIdentityServiceProvider()
  const { createWriteStream } = require('fs')

  const wstream = createWriteStream(filename, { flags: 'w+' })
  const params = {
    UserPoolId,
    GroupName,
    Limit,
  }
  try {
    while (true) {
      const res = await cognitoIdp.listUsersInGroup(params).promise()
      const usernames = res.Users.map((i) => i.Username)
      console.log(usernames)
      wstream.write(`${JSON.stringify(usernames)}\n`) // Newline JSON
      if (undefined === res.NextToken) {
        break
      } else {
        params.NextToken = res.NextToken
      }
    }
  } catch (e) {
    console.error(e)
  } finally {
    wstream.end()
  }
}
```

### Add Users To Group

```javascript
async function addUserIdsToGroup({ UserPoolId, GroupName, UserIdArray }) {
  const AWS = require('aws-sdk')
  const cognitoIdp = new AWS.CognitoIdentityServiceProvider()

  try {
    for (const user of UserIdArray) {
      const res = await cognitoIdp
        .adminAddUserToGroup({ UserPoolId, GroupName, Username: user })
        .promise()
      console.log(res)
    }
  } catch (e) {
    console.error(e)
  }
}
```

### Handle Additional Provider Sign Up Error

```
error_description: Already found an entry for username Facebook_10155611263152353
```
