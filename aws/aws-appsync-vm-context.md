# APPSYNC VTL

## Summary

Notes on using VTL with appsync

## Resources

- [Context](https://docs.aws.amazon.com/appsync/latest/devguide/resolver-context-reference.html)

### Cognito Identity Shape

- [Identity Shapes](https://docs.aws.amazon.com/appsync/latest/devguide/resolver-context-reference.html#aws-appsync-resolver-context-reference-identity)

AWS_IAM

```
{
    "accountId" : "string",
    "cognitoIdentityPoolId" : "string",
    "cognitoIdentityId" : "string",
    "sourceIp" : ["string"],
    "username" : "string", // IAM user principal
    "userArn" : "string",
    "cognitoIdentityAuthType" : "string", // authenticated/unauthenticated based on the identity type
    "cognitoIdentityAuthProvider" : "string" // the auth provider that was used to obtain the credentials
}
```

AMAZON_COGNITO_USER_POOLS

```
{
    "sub" : "uuid",
    "issuer" : "string",
    "username" : "string"
    "claims" : { ... },
    "sourceIp" : ["x.x.x.x"],
    "defaultAuthStrategy" : "string"
}
```

### Access Custom Attribute

```vtl
$context.identity.claims.get("custom:CustomAttr1")
```

### Access Authorization Cookie In Lambda

request headers must be passed thru vtl in to lambda

```vtl
{
  "operation": "Invoke",
  "payload": $util.toJson($context.request)
}
```

```javascript
exports.handler = async (event, context) => {
  console.log(event.headers)
  return {
    id: '1234goodforme',
  }
}
```
