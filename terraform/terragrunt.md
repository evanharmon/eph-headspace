# TERRAGRUNT

## Summary

Notes on working with terragrunt

## Resources

- [Docs](https://terragrunt.gruntwork.io/docs)
- [Working With Multiple AWS Accounts](https://terragrunt.gruntwork.io/docs/features/work-with-multiple-aws-accounts/)

## Clear Cache

- [Caching](https://terragrunt.gruntwork.io/docs/features/caching/)

```console
find . -maxdepth 3 -type d -name ".terragrunt-cache" -prune -exec rm -rf {} \;
```

## Debug Error Codes

```console
terragrunt plan-all --detailed-exitcode
```
