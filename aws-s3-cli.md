# AWS S3 CLI

## Create Bucket
`aws s3 mb s3://mybucket`

## Copy File Locally From S3
`aws s3 cp s3://mybucket/test.txt test2.txt`

## Copy File Local To S3
`aws s3 cp test.txt s3://mybucket/test2.txt`

## Check How Much Is In An S3 bucket
`aws s3 ls s3://mybucket --recursive --human-readable --summarize`

## Delete Objects In A Bucket
```
$ aws s3api delete-objects \
    --bucket serverless-chatbot-dev-uploads-hss \
    --delete Objects=[{Key=277ebc9.jpg}],Quiet=false
```

## Move Bucket With Files
```
$ aws s3 mv \
    --recursive \
    s3://hss-old-cf-templates-us-west-2 \
    s3://hss-new-cf-templates-us-west-2
```

## Tagging
S3 Object must be uploaded first, then tagged

## Get Version Of Objects
use --prefix to search nested folders
```
$ aws s3api list-object-versions \
    --bucket "cf-templates-us-west-2" \
    --prefix "hss"
```
