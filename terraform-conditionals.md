# TERRAFORM CONDITIONALS

## Summary

Notes on working with Terraform conditionals

## Resources

[Docs](https://www.terraform.io/docs/configuration-0-11/interpolation.html#conditionals)

## Example OR

```hcl
name = "${local.env == "sandbox" ? "main-sandbox" : "main"}"
```
