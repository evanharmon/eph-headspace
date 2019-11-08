# AWS ECR

## Summary

Notes on using the ECS ECR docker repository

## Resources

[Pull From ECR](https://docs.aws.amazon.com/AmazonECR/latest/userguide/docker-pull-ecr-image.html)

## GOTCHAS

#### Missing / Empty TAG

ECR will pull the topmost image - even if one lower in the list is latest!
Always make sure your pulling a tagged named image!

## Cross-Account Pull Permissions

ECR permissions policy

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "EcrAllowCodeBuild",
      "Effect": "Allow",
      "Principal": {
        "Service": "codebuild.amazonaws.com",
        "AWS": [
          "arn:aws:iam::111111111111:root",
          "arn:aws:iam::222222222222:root"
        ]
      },
      "Action": [
        "ecr:BatchCheckLayerAvailability",
        "ecr:BatchGetImage",
        "ecr:GetDownloadUrlForLayer"
      ]
    }
  ]
}
```

## Pull By Untagged Digest

```console
docker pull aws_account_id.dkr.ecr.us-west-2.amazonaws.com/amazonlinux:@sha256:1234
```
