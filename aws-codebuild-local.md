# AWS CODEBUILD LOCAL

## Summary

Notes on using AWS Codebuild docker image locally

## Resources

[GitHub](https://github.com/aws/aws-codebuild-docker-images/tree/master/local_builds)

## Get Docker Image

```console
docker pull amazon/aws-codebuild-local:latest
```

## Use CodeBuild Local Script

[Download Script](https://github.com/aws/aws-codebuild-docker-images/blob/master/local_builds/codebuild_build.sh)

```console
sh codebuild_build.sh \
  -i 999999999999.dkr.ecr.us-east-1.amazonaws.com/codebuild/cypress/base:10 \
  -a artifacts \
  -b buildspec.yml -c
```
