# TERRAFORM TEMPLATE_FILE

## Summary

Notes on working with the data "template_file" in Terraform

## Review Rendering

```console
tf state show data.template_file.storage_policy
```

## Conditional If Statement

```
"aws:userId": [%{ if "${env}" == "prod" } "${id_one}" %{ else } "${id_two}, ${id_three}" %{ endif ~}]
```

## Debug Generated Template File

```
resource "null_resource" "debug_policy" {
  provisioner "local-exec" {
    command = "echo \"${data.template_file.policy.rendered}\" > policy.generated.json"
  }
}

```
