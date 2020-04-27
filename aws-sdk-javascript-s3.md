# AWS SDK JAVASCRIPT S3

## Summary

Notes on working with the javascript aws sdk and S3

## Resources

- [Docs](https://docs.aws.amazon.com/AWSJavaScriptSDK/latest/AWS/S3.html)

## Instanciate Client

```javascript
import AWS from 'aws-sdk'
const s3 = new AWS.S3()
```

## Get Object Size (HEAD)

```javascript
const params = {
  Bucket: 'examplebucket',
  Key: 'HappyFace.jpg',
}
await s3.headObject(params).promise()
```
