# TERRAFORM BACKEND

## Summary

Notes on backend configuration and use in Terraform

## Assume Role With S3 Remote Backend

- [Github Issue](https://github.com/hashicorp/terraform/issues/13690)

```hcl
terraform {
  backend "s3" {
    encrypt      = "true"
    bucket       = "myapp-terraform-remote-state-stg"
    key          = "myapp/terraform.tfstate"
    role_arn     = "arn:aws:iam::999999999999:role/service-role/my-service-role"
    session_name = "my-service-role"
  }

  # introduction of Local Values configuration language feature
  required_version = ">= 0.10.3"
}
```
