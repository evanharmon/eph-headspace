# AWS S3 CROSS REPLICATION
Delete markers are replicated

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
