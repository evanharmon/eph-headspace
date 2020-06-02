# TERRAFORM AWS COGNITO

## Summary

Notes on using terraform with AWS COGNITO service

## Create Cognito User Pool

default is `Username` attribute section. To use `Email Address or phone number`
attribute setting, use `username_attributes` property in the resource as below

```terraform
resource "aws_cognito_user_pool" "mycribspool" {
  name = "mycribspool"

  username_attributes = ["email", "phone_number"]

  ...
}
```
