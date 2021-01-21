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

### DB Proxy

proxy hook up is just an IAM policy. Resource ARN for iam policy can be
generated from db proxy arn.

```console
terraform console
> replace("arn:aws:rds:us-east-1:xxxxxxxxxxxx:db-proxy:prx-xxxxxxxxxxxxxxxxx", "db-proxy", "dbuser")
arn:aws:rds:us-east-1:xxxxxxxxxxxx:dbuser:prx-xxxxxxxxxxxxxxxxx
```

make sure the security group has access rule to allow outbound traffic!
