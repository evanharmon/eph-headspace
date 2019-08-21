# AWS APPSYNC

## Summary

Notes on using aws appsync

## Resources

[AWS Tutorials](https://docs.aws.amazon.com/appsync/latest/devguide/tutorials.html)
[Resolver Mapping](https://docs.aws.amazon.com/appsync/latest/devguide/resolver-mapping-template-reference-overview.html)
[Resolver VTL Programming](https://docs.aws.amazon.com/appsync/latest/devguide/resolver-mapping-template-reference-programming-guide.html)
[VTL Utility Functions](https://docs.aws.amazon.com/appsync/latest/devguide/resolver-util-reference.html)
[Security](https://docs.aws.amazon.com/appsync/latest/devguide/security.html)
[Authorization Use Cases](https://docs.aws.amazon.com/appsync/latest/devguide/security-authorization-use-cases.html)
[Resoure For Gotchas](https://www.integralist.co.uk/posts/cognito/#example-google-app-configuration)

## Auth

[Cognito Scenarios](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-scenarios.html#scenario-appsync)
Can be Cognito User Pool or Identity Pool

[Resource For Mobile Auth]([Resoure For Gotchas](https://www.integralist.co.uk/posts/cognito/#example-google-app-configuration)

## Appsync Admin / Public Separate APIs

Note that subscriptions won't be supported

## Subscriptions

## Subscription Spam

Remember to filter subscription event responses. Subscription events are likely
global. Situation could occur where a page constantly refreshes when EVERY user
makes a call to that specific graphql mutation!!

#### Subscription Event Response Shape

```json
{
  "provider": {
    "_config": { "clientId": "11111111-1111-1111-1111-111111111111" },
    "_clientsQueue": { "promises": {} },
    "_topicObservers": {},
    "_topicClient": {},
    "_topicAlias": {}
  },
  "value": {
    "data": {
      "onCreateFile": {
        "id": "22222222-2222-2222-2222-222222222222",
        "name": "name123"
      }
    }
  }
}
```

#### Fields Received In Subscription

A subscription event on a mutation / query, only returns the fields requested by
the original consumer of that appsync call.

Example consumer mutation:

```gql
createFile() {
  id
  name
}
```

Event subscriber will receive the fields `id` and `name`
