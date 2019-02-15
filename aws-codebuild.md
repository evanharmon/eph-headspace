# AWS CODEBUILD

## Summary

Notes on using aws codebuild

## Errors

#### BUILD_CONTAINER_UNABLE_TO_PULL_IMAGE

[Fix](https://docs.aws.amazon.com/codebuild/latest/userguide/sample-ecr.html)

Add a resource policy similar to the below to your ECR repository

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "CodeBuildAccess",
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam::AWS-account-ID:root"
      },
      "Action": [
        "ecr:GetDownloadUrlForLayer",
        "ecr:BatchGetImage",
        "ecr:BatchCheckLayerAvailability"
      ]
    }
  ]
}
```
