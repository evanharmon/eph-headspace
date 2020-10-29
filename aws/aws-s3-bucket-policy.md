# AWS S3 BUCKET POLICY

## Summary

Notes on working with S3 bucket policies

## List Of Actions

differs from IAM!

- [S3 Bucket Policy Actions](https://docs.aws.amazon.com/AmazonS3/latest/dev/using-with-s3-actions.html)
- [S3 Bucket Policy Conditions](https://docs.aws.amazon.com/AmazonS3/latest/dev/amazon-s3-policy-keys.html)
- [S3 Policy Role Conditions](https://docs.aws.amazon.com/cognito/latest/developerguide/iam-roles.html)
- [Allow Cross-Account Bucket Access](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-s3/)
- [Enforce Object Ownership To Bucket Owner](https://aws.amazon.com/blogs/aws/amazon-s3-update-three-new-security-access-control-features/)

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

## Default CORS

```xml
<?xml version="1.0" encoding="UTF-8"?>
<CORSConfiguration xmlns="http://s3.amazonaws.com/doc/2006-03-01/">
  <CORSRule>
      <AllowedOrigin>*</AllowedOrigin>
      <AllowedMethod>GET</AllowedMethod>
      <MaxAgeSeconds>3000</MaxAgeSeconds>
      <AllowedHeader>*</AllowedHeader>
  </CORSRule>
</CORSConfiguration>
```

## Limit Bucket Access To CloudFront

[AWS Bucket Policy Example](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-bucket-policies.html#example-bucket-policies-use-case-6)

```json
{
  "Version": "2012-10-17",
  "Id": "PolicyForCloudFrontPrivateContent",
  "Statement": [
    {
      "Sid": " Grant a CloudFront Origin Identity access to support private content",
      "Effect": "Allow",
      "Principal": {
        "CanonicalUser": "aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
      },
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::examplebucket/*"
    }
  ]
}
```

## Limit Object Access To Cognito Identity Pool Id

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Action": ["s3:ListBucket"],
      "Effect": "Allow",
      "Resource": ["arn:aws:s3:::mybucket"],
      "Condition": {
        "StringLike": {
          "s3:prefix": ["${cognito-identity.amazonaws.com:sub}/*"]
        }
      }
    },
    {
      "Action": ["s3:GetObject", "s3:PutObject"],
      "Effect": "Allow",
      "Resource": [
        "arn:aws:s3:::mybucket/${cognito-identity.amazonaws.com:sub}/*"
      ]
    }
  ]
}
```

## Allow Another Account User Access To Bucket

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam::AccountB:user/AccountBUserName"
      },
      "Action": ["s3:GetObject", "s3:PutObject", "s3:PutObjectAcl"],
      "Resource": ["arn:aws:s3:::AccountABucketName/*"]
    }
  ]
}
```

## Allow Another Assumed Role Access To Bucket

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam::AccountB:role/RoleName"
      },
      "Action": ["s3:GetObject", "s3:PutObject", "s3:PutObjectAcl", "s3:List*"],
      "Resource": [
        "arn:aws:s3:::AccountABucketName/*",
        "arn:aws:s3:::AccountABucketName"
      ]
    }
  ]
}
```
