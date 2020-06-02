# TERRAFORM UPGRADE

## Summary

Notes on upgrading terraform resources

## Resources

- [Upgrade to v0.12](https://www.terraform.io/upgrade-guides/0-12.html)

## Modules

Modules don't tend to have a `.terraform` folder, run the below in order to
upgrade from pre v0.12 to v0.12

```console
terraform init
terraform v0.12upgrade
```

## Resources / Terraform Init

Running tf v0.12 `terraform init` can produce a warning about syntax errors if
a `terraform.tf` terraform backend resource has a `providers` object. The
providers portion should be removed so the `terraform` resource only has the
`backend` resource

```hcl
terraform {
  backend "s3" {
    encrypt = true
    bucket  = "terraform-remote-state"
    key     = "path/to/terraform.tfstate"
    region  = "us-east-1"
    profile = "terraform"
  }

  required_version = ">= 0.10.3"
}
```

Be sure the provider is updated to a reason version such as 2.46.0

```hcl
provider "aws" {
    region  = "us-east-1"
    profile = "terraform"
    version = "~> 2.46.0"
}

provider "aws" {
    alias                   = "target-account"
    region                  = "us-east-1"
    shared_credentials_file = "/Users/myuser/.aws/prod.AdminCrossAccount"

    version                 = "~> 2.46.0"
}
```
