# AWS CODEBUILD

## Summary

Notes on using aws codebuild

## Resources

- [Env Variables Available](https://docs.aws.amazon.com/codebuild/latest/userguide/build-env-ref-env-vars.html)
- [Docker Cache Re-Use Improve Build Times](https://aws.amazon.com/blogs/devops/reducing-docker-image-build-time-on-aws-codebuild-using-an-external-cache/)

## Errors

#### BUILD_CONTAINER_UNABLE_TO_PULL_IMAGE

- [Fix](https://docs.aws.amazon.com/codebuild/latest/userguide/sample-ecr.html)

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

#### Docker Daemon Not Running

- [Doc](https://docs.aws.amazon.com/codebuild/latest/userguide/sample-docker-custom-image.html#sample-docker-custom-image-files)
  Need to start dockerd - might be in `/usr/local/bin` or `/usr/bin`

```console
nohup /usr/local/bin/dockerd --host=unix:///var/run/docker.sock --host=tcp://127.0.0.1:2375 --storage-driver=overlay2&
timeout 15 sh -c "until docker info; do echo .; sleep 1; done"
```
