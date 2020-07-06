# DOKER TAGS

## Summary

Notes on docker tagging

## Resources

- [MSDN Best Practices Tagging](https://blogs.msdn.microsoft.com/stevelasker/2018/03/01/docker-tagging-best-practices-for-tagging-and-versioning-docker-images/)
- [K8S Container Image Tagging](https://kubernetes.io/docs/concepts/configuration/overview/)
- [Tagging With ECR](https://vsupalov.com/docker-latest-tag/)

## Tag Example For ECR

```console
docker tag \
  $AWS_ACCOUNT_ID.dkr.ecr.$AWS_DEFAULT_REGION.amazonaws.com/namespace/app:latest \
  namespace/app:latest
```
