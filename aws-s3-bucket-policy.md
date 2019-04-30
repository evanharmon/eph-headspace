# AWS S3 BUCKET POLICY

## Summary

Notes on working with S3 bucket policies

## List Of Actions

differs from IAM!
[AWS](https://docs.aws.amazon.com/AmazonS3/latest/dev/using-with-s3-actions.html)

## Invalid Action Errors

Beware of `s3:PutAccountPublicAccessBlock` and `s3:GetAccountPublicAccessBlock`.
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
