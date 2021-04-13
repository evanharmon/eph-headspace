# AWS AMPLIFY

## Summary

Notes on using aws amplify sdk's, cli, etc

## Resources

- [AWS Blog Analytics None DataSource Subscriptions](https://aws.amazon.com/blogs/mobile/visualizing-big-data-with-aws-appsync-amazon-athena-and-aws-amplify/)

## Custom API Gateway Headers

```javascript
Amplify.configure({
  API: {
    endpoints: [
      {
        name: 'sampleCloudApi',
        endpoint: 'https://xyz.execute-api.us-east-1.amazonaws.com/Development',
        custom_header: async () => {
          return { Authorization: 'token' }
          // Alternatively, with Cognito User Pools use this:
          // return {
          //   Authorization: (await Auth.currentSession())
          //     .getIdToken()
          //     .getJwtToken(),
          // }
        },
      },
    ],
  },
})
```

### Custom Graphql Headers

```javascript
Amplify.configure({
  API: {
    graphql_headers: async () => ({
      'My-Custom-Header': 'my value',
    }),
  },
})
```

### Pass Custom Attributes

Only the ID token has custom claims and given_name, surname.
Access token does NOT contain them

```javascript
API: {
  graphql_endpoint: 'https://****.appsync-api.***.amazonaws.com/graphql',
  graphql_region: '***',
  graphql_authenticationType: 'AMAZON_COGNITO_USER_POOLS',
  graphql_headers: async () => {
    try {
      const token = (await Auth.currentSession()).idToken.jwtToken;
      return { Authorization: token }
    }
    catch (e) {
      console.error(e);
      return {};
      // Potentially you can retrieve it from local storage
    }
  }
}
```
