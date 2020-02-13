# TERRAFORM RECIPES

## Summary

Delicious

## Resources

- [v12 Changes](https://www.hashicorp.com/blog/hashicorp-terraform-0-12-preview-for-and-for-each/)

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

## Output Multiple Objects

in TF v0.12, now entire objects can be outputed in multiples, allowing
the consumer drill down for the id, name, etc

```
output "public_subnets" {
  description = "List of IDs of public subnets"
  value       = aws_subnet.public
}
```

## Output Multiple Resource IDs As Map For Loop

```
output "private_subnets" {
  description = "List of IDs of private subnets"
  value = {
    for subnet in aws_subnet.private :
    subnet.id => subnet.id
  }
}
```

## Ouput Multiple Resources As Map In For Loop

```
output "instance_private_ip_addresses" {
  # Result is a map from instance id to private IP address, such as:
  #  {"i-1234" = "192.168.1.2", "i-5678" = "192.168.1.5"}
  value = {
    for instance in aws_instance.example:
    instance.id => instance.private_ip
  }
}
```

## Pass Multiple Data Object Values As List

```
private_subnet_ids = [for subnet in data.terraform_remote_state.networking.outputs.private_subnets : tostring(subnet.id)]
```

## Use data.terraform_remote_state

```
data "terraform_remote_state" "store" {
  backend = "s3"

  config = {
    bucket  = "my-bucket"
    encrypt = true
    key     = "/store/terraform.tfstate"
    profile = "terraform"
    region  = "us-east-1"
  }

  workspace = "default"
}
```

## For Loop

```hcl
cidr_blocks = [
  for num in var.subnet_numbers:
  cidrsubnet(data.aws_vpc.example.cidr_block, 8, num)
]
```

## Multiple Data Parameter Store Objects

```hcl
data "aws_ssm_parameter" "list" {
  count = length(var.param_list)
  name  = var.param_list[count.index]
}
```

## Stringify List Of Number Values

```hcl
cidr_blocks = [for subnet in aws_subnet.mysubnet : tostring(subnet.cidr_block)]
```

## Join StringList From Parameter Store With Another List

```hcl
list = concat(split(",", join(",", [for param in data.aws_ssm_parameter.list : param.value])), local.other_list)
```
