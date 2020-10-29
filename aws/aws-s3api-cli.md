# AWS S3API CLI

## Resources

## Delete Objects In A Bucket

```console
aws s3api delete-objects \
  --bucket serverless-chatbot-dev-uploads-hss \
  --delete Objects=[{Key=277ebc9.jpg}],Quiet=false
```

## Get Version Of Objects

use --prefix to search nested folders

```console
aws s3api list-object-versions \
  --bucket "cf-templates-us-west-2" \
  --prefix "hss"
```

## List Multi Part Uploads

```console
aws s3api list-multipart-uploads \
  --bucket "my-bucket-name" \
  --prefix "hss"
```

## Change Object Ownership

```console
aws s3api put-object-acl --bucket destination_awsexamplebucket --key keyname --acl bucket-owner-full-control
```
