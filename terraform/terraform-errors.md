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

## statusCode Apigateway Error On

needed to avoid the error `Execution failed due to configuration error: statusCode should be an integer which defined in request template`

```hcl
resource "aws_api_gateway_integration" "options" {
  http_method          = "${aws_api_gateway_method.options.http_method}"
  resource_id          = "${aws_api_gateway_resource.this.id}"
  rest_api_id          = "${aws_api_gateway_rest_api.this.id}"
  type                 = "MOCK"
  passthrough_behavior = "WHEN_NO_MATCH"

  // needed to avoid the error `Execution failed due to configuration error: statusCode should be an integer which defined in request template`
  request_templates = {
    "application/json" = <<EOT
    {"statusCode": 200}
    EOT
  }
}
```

## Unsupported Attribute
Instance data.aws_region.cross-account data could not be decoded from the
state: unsupported attribute "current".

in this case - had to do `terraform state rm data.aws_region.cross-account`
and then run a new plan
