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

## Append Timestamp To Resource Name

```
resource "some_resource" "foo" {
    # Change 8 for your desired substring length of timestamp
    name = "my-thing-${substr(replace(timestamp(), "/[-:]/", ""), 0, 8)}"
    lifecycle {
        ignore_changes = ["name"]
    }
}
```

or

```
locals {
  timestamp = "${replace(timestamp(), "/[-:TZ]/", "")}000000000000000000"
}
```

## Join Single Item With List

```
speciallist = concat([aws_cloudfront_origin_access_identity.main.iam_arn], var.my_arn_list)
```
