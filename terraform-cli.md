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

## Resources

#### Destroy entire module
```console
terraform destroy --target=module.mymod
```
