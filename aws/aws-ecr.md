# AWS ECR

## Summary

Notes on using the ECS ECR docker repository

## Resources

- [Pull From ECR](https://docs.aws.amazon.com/AmazonECR/latest/userguide/docker-pull-ecr-image.html)
- [Grant Separate Account User Access](https://aws.amazon.com/premiumsupport/knowledge-center/secondary-account-access-ecr/)

## GOTCHAS

#### Missing / Empty TAG

ECR will pull the topmost image - even if one lower in the list is latest!
Always make sure your pulling a tagged named image!

## Cross-Account Pull Permissions

### Service Role On Account

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

### Specific User On Another Account

````json
{
    "Version": "2008-10-17",
    "Statement": [
        {
            "Sid": "AllowPushPull",
            "Effect": "Allow",
            "Principal": {
                "AWS": [
                    "arn:aws:iam::123456789012:user/push-pull-user-1",
                    "arn:aws:iam::123456789012:user/push-pull-user-2"
                ]
            },
            "Action": [
                "ecr:GetDownloadUrlForLayer",
                "ecr:BatchGetImage",
                "ecr:BatchCheckLayerAvailability",
                "ecr:PutImage",
                "ecr:InitiateLayerUpload",
                "ecr:UploadLayerPart",
                "ecr:CompleteLayerUpload"
            ]
        }
    ]
}
```

## Pull By Untagged Digest

```console
docker pull aws_account_id.dkr.ecr.us-east-1.amazonaws.com/amazonlinux:@sha256:1234
````

### Push To ECR

first re-tag to ECR namespace if necessary, then push

```console
docker tag namespace/myapp aws_account_id.dkr.ecr.us-east-1.amazonaws.com/namespace/myapp:latest
docker push aws_account_id.dkr.ecr.us-east-1.amazonaws.com/namespace/myapp:latest
```

### Re-tag ECR

download old sha then re-tag via docker commands

```console
docker pull \
  aws_account_id.dkr.ecr.us-east-1.amazonaws.com/namespace/myapp@sha256:11111
docker tag \
  aws_account_id.dkr.ecr.us-east-1.amazonaws.com/namespace/myapp@sha256:11111 \
  aws_account_id.dkr.ecr.us-east-1.amazonaws.com/namespace/myapp:dev
docker push \
  aws_account_id.dkr.ecr.us-east-1.amazonaws.com/namespace/myapp:dev
```
