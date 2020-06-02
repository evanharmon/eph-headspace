# AWS CLOUD TRAIL

## Summary

Notes on using cloudtrail for auditing, logging

## Resources

[Receive Logs From Multiple Accounts](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-receive-logs-from-multiple-accounts.html)
[Turning On Cloudtrail In Multiple Accounts](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/turn-on-cloudtrail-in-additional-accounts.html)
[S3 Server Access Logging vs CloudTrail](https://www.netskope.com/blog/aws-s3-logjam-server-access-logging-vs-object-level-logging)
[S3 Bucket Policy For CloudTrail Multiple Accounts](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-set-bucket-policy-for-multiple-accounts.html)

## Logging CloudTrails To Other Accounts

See resource links above

- S3 Bucket policy has to be adjusted to allow other accounts put access
- S3 Bucket ACL has to be adjusted to give access to each account's canonical id
- First CloudTrail to the bucket MUST be the same account where the bucket resides

## Logs

- logs delivered every 5 minutes
- logs can be aggregated to single file from multiple regions in to single
  bucket

## S3 Bucket Policy Example Multiple Accounts

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AWSCloudTrailAclCheck20131101",
      "Effect": "Allow",
      "Principal": {
        "Service": "cloudtrail.amazonaws.com"
      },
      "Action": "s3:GetBucketAcl",
      "Resource": "arn:aws:s3:::myBucketName"
    },
    {
      "Sid": "AWSCloudTrailWrite20131101",
      "Effect": "Allow",
      "Principal": {
        "Service": "cloudtrail.amazonaws.com"
      },
      "Action": "s3:PutObject",
      "Resource": [
        "arn:aws:s3:::myBucketName/[optional] myLogFilePrefix/AWSLogs/111111111111/*",
        "arn:aws:s3:::myBucketName/[optional] myLogFilePrefix/AWSLogs/222222222222/*"
      ],
      "Condition": {
        "StringEquals": {
          "s3:x-amz-acl": "bucket-owner-full-control"
        }
      }
    }
  ]
}
```
