# AWS S3 CLI

## Resources

- [Canned ACLS](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#canned-acl)
- [Multi Part Upload](https://aws.amazon.com/premiumsupport/knowledge-center/s3-multipart-upload-cli/)

## Create Bucket

```console
aws s3 mb s3://mybucket
```

## Copy File Locally From S3

```console
aws s3 cp s3://mybucket/test.txt test2.txt
```

## Copy File Local To S3

```console
aws s3 cp test.txt s3://mybucket/test2.txt
```

## Check How Much Is In An S3 bucket

```console
aws s3 ls s3://mybucket --recursive --human-readable --summarize
```

## Copy Bucket With Files

```console
aws s3 cp --recursive s3://old-bucket s3://new-bucket
```

## Copy Bucket To Another Account

This is best done by adding policy statements on the original bucket allowing
access from an assumed role. Do the copy below, then remove the temporary s3
bucket policy statements

```console
aws s3 cp --recursive --acl bucket-owner-full-control s3://old-bucket s3://new-bucket
```

## Move Bucket With Files

```console
aws s3 mv --recursive s3://old-bucket s3://new-bucket
```

## Tagging

S3 Object must be uploaded first, then tagged

## Cross Account Sync Support

Write from a producer account(111111111111) to a source account (222222222222)
bucket. Be able to read from a consumer account (333333333333) from source
account bucket.

source account s3 bucket policy

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "sync access",
      "Effect": "Allow",
      "Principal": {
        "AWS": [
          "arn:aws:iam::111111111111:root",
          "arn:aws:iam::222222222222:root",
          "arn:aws:iam::333333333333:root"
        ]
      },
      "Action": ["s3:List*", "s3:Get*"],
      "Resource": ["arn:aws:s3:::mybucket", "arn:aws:s3:::mybucket/*"]
    }
  ]
}
```

put objects granting owner of bucket full control, and giving read access to
consumer account. Uses canonical ids of each account as ids

```console
aws s3 sync test-dir s3://mybucket \
  --grants read=id=cccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccc \
           readacl=id=cccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccc \
           full=id=bbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbb
```
