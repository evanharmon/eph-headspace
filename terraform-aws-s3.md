# TERRAFORM AWS S3

## Summary

Notes on managing S3 terraform

## Resources

- [Docs S3 Bucket Notifications](https://www.terraform.io/docs/providers/aws/r/s3_bucket_notification.html)

### Bucket Events
If receiving a 400 error, make sure the `aws_lambda_permission.bucket_allow`
has been added in the terraform
