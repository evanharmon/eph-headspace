# AWS ECR

## Summary

Notes on using the ECS ECR docker repository

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
