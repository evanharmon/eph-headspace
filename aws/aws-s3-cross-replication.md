# AWS S3 CROSS REPLICATION

Delete markers are replicated

## Summary

## Resources

[Same Region Replication](https://aws.amazon.com/about-aws/whats-new/2019/09/amazon-s3-introduces-same-region-replication/)

## Same Region Replication

any changes to the object, metadata, ACLs, or object tags trigger a new
replication to the destination bucket

## Limitations

- requires versioning enabled on source bucket
- only affects new uploads
- no daisy chaining

## Cross Account Role Action Permissions

```json

```

## Required S3 Bucket Policy

```json
  "Action": [
      "s3:ReplicateDelete",
      "s3:ReplicateObject",
      "s3:GetBucketVersioning",
      "s3:PutBucketVersioning",
      "s3:ObjectOwnerOverrideToBucketOwner"
  ],
```
