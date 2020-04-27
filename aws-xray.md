# AWS XRAY

## Summary

Notes on using xray tracing in AWS

## Resources

- [SNS Tracing](https://docs.aws.amazon.com/xray/latest/devguide/xray-services-sns.html)
- [Instrument NodeJS](https://docs.aws.amazon.com/lambda/latest/dg/nodejs-tracing.html)

## Lambda

### Trace AWS SDK

```console
const AWSXRay = require('aws-xray-sdk-core')
const AWS = AWSXRay.captureAWS(require('aws-sdk'))
const s3 = new AWS.S3()
```
