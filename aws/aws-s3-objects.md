# AWS S3 OBJECTS

## Summary

Notes on using S3 Objects

## User-Defined Object Metadata

[AWS Doc](https://docs.aws.amazon.com/AmazonS3/latest/user-guide/add-object-metadata.html)

## Presigned URLs

[Max Expiration](https://aws.amazon.com/premiumsupport/knowledge-center/presigned-url-s3-bucket-expiration/)

### Etag

Multipart upload etags are two parts. Example

```json
{
    "ETag": "\\"exampleae01633ff0af167d925cad279-2\\"",
    "Bucket": "exampleawsbucket",
    "Location": "https://exampleawsbucket.s3.amazonaws.com/large_test_file",
    "Key": "large_test_file"
}
```
