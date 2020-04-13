# TERRAFORM FUNCTIONS

## Summary

Notes on using functions in terraform templates

## Resources

[Docs](https://www.terraform.io/docs/configuration/functions.html)

## Grab First Element

helps with the `element() may not be used with an empty list` error

```hcl
"${element(concat(aws_cognito_user_pool_client.web.*.id, list("")), 0)}"
```

## Typical Element Use

use index syntax `var.my_list[count.index]`

Only use `element()` when wrap-around index behavior is necessary

## Strings

Uppercase

```hcl
upper()
```

Convert int to string

```hcl
tostring()
```

## Flatten

- [Docs](https://www.terraform.io/docs/configuration/functions/flatten.html)

if trying to stringify a list and getting the error 'is tuple with X elements'
try flattening

## Lookup Value And Set Default

```console
lookup({a="ay", b="bee"}, "a", "what?")
```
