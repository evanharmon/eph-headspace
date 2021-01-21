# AWS SERVICE QUOTAS CLI

## Summary

Notes on using the service-quotas cli

## Resources

- [Docs](https://docs.aws.amazon.com/cli/latest/reference/service-quotas/index.html#cli-aws-service-quotas)

## List Services

```console
aws service-quotas list-services
```

## Get List Default Service Quota Codes

```console
aws service-quotas list-aws-default-service-quotas --service-code lambda
```

## Get Default Service Quota

```console
aws service-quotas get-aws-default-service-quota --service-code lambda --quota-code L-B99A9384
```

## Get Service Quota

Nothing will be returned if aws default account quota limit is the only limit in
place for the service / metric

```console
aws service-quotas get-service-quota --service-code lambda --quota-code L-B99A9384
```
