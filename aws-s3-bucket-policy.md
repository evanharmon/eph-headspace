# AWS S3 BUCKET POLICY

## Summary

Notes on working with S3 bucket policies

## List Of Actions

differs from IAM!
[S3 Bucket Policy Actions](https://docs.aws.amazon.com/AmazonS3/latest/dev/using-with-s3-actions.html)
[S3 Bucket Policy Concditions](https://docs.aws.amazon.com/AmazonS3/latest/dev/amazon-s3-policy-keys.html)

## Invalid Action Errors

#### `s3:PutAccountPublicAccessBlock` and `s3:GetAccountPublicAccessBlock`.

Both only support the `*` as Resource

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "statement1",
      "Effect": "Allow",
      "Action": ["s3:GetAccountPublicAccessBlock"],
      "Resource": ["*"]
    }
  ]
}
```

#### `s3:PutBucketObjectLockConfiguration`

bucket level resource! does not support sub resources

## Deny Multiple AND Conditions

[AWS Forum Post](https://forums.aws.amazon.com/thread.jspa?messageID=603265)
Allow IP controlled access to s3 bucket hosted website and CDN access.

```
When specifying conditions with different tag identifiers the conditions are
considered separate. By default, conditions are evaluated with an AND when
combined in a single statement. In order to perform an OR action across
different conditions you need to put them in separate statements
```

```json
{
  "Version": "2012-10-17",
  "Id": "IPAccessControl",
  "Statement": [
    {
      "Sid": "PublicReadBucketObjects",
      "Effect": "Deny",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "${bucket_arn}/*",
      "Condition": {
        "NotIpAddress": {
          "aws:SourceIp": ["1.1.1.1"]
        },
        "ArnNotLike": {
          "aws:PrincipalArn": "${origin_access_identity_arn}"
        }
      }
    }
  ]
}
```

## Prevent Bucket Lockout

S3 Buckets can be locked out by incorrect / inadvertent changes to the bucket policy

#### Testing / Debugging Best Practices

- Keep a base policy in at all times to prevent lockout
- Use a separate AWS account for testing where you have ROOT access
