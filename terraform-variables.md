# TERRAFORM VARIABLES

## Summary

Notes on using Terraform variables

## Resources

- [Docs](https://www.terraform.io/docs/configuration/variables.html)

## Variable Types

- string
- number
- bool

## Use Variable Object

tfvars file

```env
feature_flags = {
  flag1: "true"
  flag2: "false"
}
```

variable declaration in `variables.tf`

```hcl
variable "feature_flags" {
  description = "my custom description"
  type = object({
    flag1 = string
    flag2 = string
  })
}
```

Access Variable Object Properties

```hcl
setting = var.feature_flags.flag1
```
