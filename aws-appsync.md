# AWS APPSYNC

## Summary

Notes on using aws appsync

## Resources

- [AWS Tutorials](https://docs.aws.amazon.com/appsync/latest/devguide/tutorials.html)
- [Resolver Mapping](https://docs.aws.amazon.com/appsync/latest/devguide/resolver-mapping-template-reference-overview.html)
- [Resolver VTL Programming](https://docs.aws.amazon.com/appsync/latest/devguide/resolver-mapping-template-reference-programming-guide.html)
- [VTL Utility Functions](https://docs.aws.amazon.com/appsync/latest/devguide/resolver-util-reference.html)
- [Resource For Gotchas](https://www.integralist.co.uk/posts/cognito/#example-google-app-configuration)
- [Pure WebSocket Support](https://aws.amazon.com/about-aws/whats-new/2019/11/aws-appsync-adds-real-time-enhancements-with-pure-websockets-support-for-graphql-subscriptions/)

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
