# AWS LAMBDA NODE.JS

## Summary

Notes on working with lambda's written in Node.js

## Resources

- [Async / Await](https://aws.amazon.com/blogs/compute/node-js-8-10-runtime-now-available-in-aws-lambda/)
- [Stream S3](https://docs.aws.amazon.com/sdk-for-javascript/v2/developer-guide/requests-using-stream-objects.html)
- [Context Object](https://docs.aws.amazon.com/lambda/latest/dg/nodejs-context.html)

## Access Credentials For Function

available as environment variables

```console
AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY
AWS_SESSION_TOKEN
```

### Check Identity Via Context

Will only work if called with identity pool NOT user pool

```console
exports.handler = async function(event, context) {
  console.log('Remaining time: ', context.getRemainingTimeInMillis())
  console.log('Function name: ', context.functionName)
  return context.logStreamName
}
```

### AWS SDK

- [SDK Version By Node Version](https://docs.aws.amazon.com/lambda/latest/dg/lambda-runtimes.html)

Lambda's include the AWS SDK by default

### Tests

Inline test in `index.js` that only runs when invoked from CLI

```javascript
if (!module.parent) { console.log(do test lines here) }
```
