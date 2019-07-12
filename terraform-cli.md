# TERRAFORM CLI

## Summary

Notes on using the terraform CLI

## State

#### Remove a root level resource

```console
terraform state rm aws_iam_service_linked_role.autoscaling
```

#### Remove entire module

```console
terraform state rm module.mymod
```

#### Taint module

```console
terraform taint --module=my-module aws_iam_role.my_role
```

#### Move To Another State File

Note: Be careful not to have a resource controlled by two state files!
Terraform does not support moving modules or resources between two s3 tfstate
files. Copy the state file to the new location in s3 and remove any modules
or resources not in use.

## Resources

[TF Plan](https://www.terraform.io/docs/commands/plan.html)

#### Destroy entire module

```console
terraform destroy --target=module.mymod
```

#### Move `main.tf` resources in to modules

[Blog](https://ryaneschinger.com/blog/terraform-state-move/)

Remove resource from main.tf file, add to `modules/mymodule/main.tf` file, then:

```console
terraform state mv aws_elb.weblb module.web.aws_elb.weblb
```

## Show Details Of A Resource

```console
terraform state show module.storage.aws_iam_role_policy.auth
```

## Pass Variables To Plan

```console
terraform plan -out=tfplan -var env=sandbox
```

## Limit Plan To Modules

```console
terraform plan -out=tfplan --target=module.appsync
```

## Outputs Not Updating

`terraform plan` will show no changes. Instead run `terraform refresh`
