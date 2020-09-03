# TERRAGRUNT MODULES

## Summary

Notes on working with terragrunt and terraform modules

## Resources

- [Docs](https://terragrunt.gruntwork.io/docs/)

### Terragrunt Paths

double backslash `//` denotes the root directory of the repo

example: `./live/dev/myapp/terragrunt.hcl` accessing `./modules/mymodule`

```hcl
terraform {
  source = "../../..//modules/mymodule"
}
inputs = {}
```
