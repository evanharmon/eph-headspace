# TERRAFORM FUNCTIONS

## Summary

Notes on using functions in terraform templates

## Resources

[Docs](https://www.terraform.io/docs/configuration/functions.html)

## Grab First Element

helps with the `element() may not be used with an empty list` error

```
"${element(concat(aws_cognito_user_pool_client.web.*.id, list("")), 0)}"
```
