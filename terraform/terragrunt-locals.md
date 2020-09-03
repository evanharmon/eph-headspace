# TERRAGRUNT LOCALS

## Summary

Notes on working with terragrunt local variables

## Resources

- [Docs](https://terragrunt.gruntwork.io/docs/features/locals/)

### Scope

`locals` variables declared in a terragrunt `hcl` file are only available
for reference in that single file

```hc
locals {
  aws_region = "us-east-1"
}

inputs = {
  aws_region  = local.aws_region
  s3_endpoint = "com.amazonaws.${local.aws_region}.s3"
}
```
