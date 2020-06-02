# AWS S3 BUCKET POLICY BASE

## Overview

Example s3 bucket base policy to secure bucket in prod

## Example 1

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AdminDeleteBucketAccess",
      "Effect": "Allow",
      "Principal": "*",
      "Action": [
        "s3:DeleteBucket",
        "s3:DeleteBucketPolicy",
        "s3:DeleteBucketWebsite"
      ],
      "Resource": "arn:aws:s3:::hss-test-bucket",
      "Condition": {
        "StringLike": {
          "aws:userid": ["s3-test-role:*", "111111111"]
        }
      }
    },
    {
      "Sid": "AdminEditBucketAccess",
      "Effect": "Allow",
      "Principal": "*",
      "Action": [
        "s3:PutBucketObjectLockConfiguration",
        "s3:PutAccelerateConfiguration",
        "s3:PutAnalyticsConfiguration",
        "s3:PutBucketLogging",
        "s3:PutBucketNotification",
        "s3:PutBucketRequestPayment",
        "s3:PutBucketTagging",
        "s3:PutBucketVersioning",
        "s3:PutBucketWebsite",
        "s3:PutEncryptionConfiguration",
        "s3:PutInventoryConfiguration",
        "s3:PutLifecycleConfiguration",
        "s3:PutMetricsConfiguration",
        "s3:PutReplicationConfiguration"
      ],
      "Resource": "arn:aws:s3:::hss-test-bucket",
      "Condition": {
        "StringLike": {
          "aws:userid": ["s3-test-role:*", "111111111"]
        }
      }
    },
    {
      "Sid": "AdminReadBucketAccess",
      "Effect": "Allow",
      "Principal": "*",
      "Action": [
        "s3:ListBucket",
        "s3:ListBucketVersions",
        "s3:ListBucketMultipartUploads"
      ],
      "Resource": "arn:aws:s3:::hss-test-bucket",
      "Condition": {
        "StringLike": {
          "aws:userid": ["s3-test-role:*", "111111111"]
        }
      }
    },
    {
      "Sid": "AdminDeleteObjectAccess",
      "Effect": "Allow",
      "Principal": "*",
      "Action": [
        "s3:DeleteObject",
        "s3:DeleteObjectTagging",
        "s3:DeleteObjectVersion",
        "s3:DeleteObjectVersionTagging"
      ],
      "Resource": "arn:aws:s3:::hss-test-bucket/*",
      "Condition": {
        "StringLike": {
          "aws:userid": ["s3-test-role:*", "111111111"]
        }
      }
    },
    {
      "Sid": "AdminEditObjectAccess",
      "Effect": "Allow",
      "Principal": "*",
      "Action": [
        "s3:PutObject",
        "s3:PutObjectAcl",
        "s3:PutObjectVersionAcl",
        "s3:PutObjectTagging",
        "s3:PutObjectVersionTagging",
        "s3:PutObjectRetention",
        "s3:PutObjectLegalHold",
        "s3:RestoreObject"
      ],
      "Resource": "arn:aws:s3:::hss-test-bucket/*",
      "Condition": {
        "StringLike": {
          "aws:userid": ["s3-test-role:*", "111111111"]
        }
      }
    },
    {
      "Sid": "AdminReadObjectAccess",
      "Effect": "Allow",
      "Principal": "*",
      "Action": [
        "s3:GetObject",
        "s3:GetObjectAcl",
        "s3:GetObjectTagging",
        "s3:GetObjectTorrent",
        "s3:GetObjectVersion",
        "s3:GetObjectVersionAcl",
        "s3:GetObjectVersionTagging",
        "s3:GetObjectVersionTorrent",
        "s3:GetObjectRetention",
        "s3:GetObjectLegalHold",
        "s3:ListMultipartUploadParts"
      ],
      "Resource": "arn:aws:s3:::hss-test-bucket/*",
      "Condition": {
        "StringLike": {
          "aws:userid": ["s3-test-role:*", "111111111"]
        }
      }
    },
    {
      "Sid": "AppEditObjectAccess",
      "Effect": "Allow",
      "Principal": "*",
      "Action": ["s3:PutObject"],
      "Resource": "arn:aws:s3:::hss-test-bucket/public/*",
      "Condition": {
        "StringLike": {
          "aws:userid": ["s3-test-role:*", "111111111"]
        }
      }
    },
    {
      "Sid": "AppReadObjectAccess",
      "Effect": "Allow",
      "Principal": "*",
      "Action": ["s3:GetObject"],
      "Resource": "arn:aws:s3:::hss-test-bucket/public/*",
      "Condition": {
        "StringLike": {
          "aws:userid": ["s3-test-role:*", "111111111"]
        }
      }
    },
    {
      "Sid": "DenyAllPreventLockout",
      "Effect": "Deny",
      "Principal": "*",
      "Action": "s3:*",
      "Resource": [
        "arn:aws:s3:::hss-test-bucket/*",
        "arn:aws:s3:::hss-test-bucket"
      ],
      "Condition": {
        "StringNotLike": {
          "aws:userid": ["s3-test-role:*", "111111111"]
        }
      }
    }
  ]
}
```
