# AWS S3 CROSS REPLICATION

Delete markers are replicated

## Summary

## Resources

- [Same Region Replication](https://aws.amazon.com/about-aws/whats-new/2019/09/amazon-s3-introduces-same-region-replication/)
- [V1 vs V2 Replication with Delete Markers](https://docs.aws.amazon.com/AmazonS3/latest/dev/replication-add-config.html#replication-backward-compat-considerations)

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

## Replication Configuration Schema Upgrade

To use priorities, XML V2 Replication is required. A `schema upgrade` must be
completed and has an effect on how
[delete markers](https://docs.aws.amazon.com/AmazonS3/latest/dev/replication-add-config.html#replication-backward-compat-considerations)
are handled.
