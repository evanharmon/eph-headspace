# AWS AMPLIFY AUTH

## Summary

Notes on using aws amplify auth sdk's, cli, etc

## Resources

[React Router Amplify Auth](https://www.rockyourcode.com/custom-react-hook-use-aws-amplify-auth/)
[Docs for JS](https://aws-amplify.github.io/docs/js/authentication)

## Sign In With Google

```javascript
Auth.federatedSignIn({ provider: "Google" });
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
  authMode: "AMAZON_COGNITO_USER_POOLS"
});
```
