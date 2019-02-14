# TERRAFORM ERRORS

## Summary

Notes on common terraform errors

## `terraform init` Error Loading Modules during CI / CD

You must delete the `.terraform` directory in between CI / CD stages.

```yaml
artifacts:
  # BAD BAD DO NOT COPY OVER .TERRAFORM
  files:
    - "**/*"
  # yamllint disable-line rule:truthy
  discard-paths: no # keep folder structure inside artifact
```
