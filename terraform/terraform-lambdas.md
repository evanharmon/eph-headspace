# TERRAFORM LAMBDA

## Summary

Notes on working with AWS Lambdas in Terraform

## Resources

- [TF Docs](https://www.terraform.io/docs/providers/aws/r/lambda_function.html)

### Configuration

#### Enable Xray

```hcl
tracing_config {
  mode = "Active"
}
```
