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

### CORS

common CORS headers needed for api calls

```json
{
  "Content-Type": "application/json; charset=UTF-8",
  "Accept": "application/json, text/plain/ */*",
  "Access-Control-Allow-Headers": "Content-Type,X-Amz-Date,Authorization,X-Amz-Security-Token",
  "Access-Control-Allow-Credentials": "true",
  "Access-Control-Allow-Methods": "DELETE,GET,HEAD,OPTIONS,PATCH,POST,PUT"
}
```

### Custom API Headers

- [Rest Api Calls](https://docs.amplify.aws/lib/restapi/authz/q/platform/js#cognito-user-pools-authorization)
