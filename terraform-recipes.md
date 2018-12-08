# TERRAFORM RECIPES

## Summary
Delicious

## Get AWS Account ID
[Doc](https://www.terraform.io/docs/providers/aws/d/caller_identity.html)
```
data "aws_caller_identity" {}
module "example" {
  account_id = "${data.aws_caller_identity.account_id}"
}
```
