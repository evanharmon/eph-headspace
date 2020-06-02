# AWS IAM CROSS ACCOUNT ROLES

## Summary

Notes on doing cross account access between AWS accounts

## Steps

[Docs](https://docs.aws.amazon.com/IAM/latest/UserGuide/tutorial_cross-account-with-roles.html)

- create role in new account, establish trust relationship with current AWS account
- add assumeRole iam policy to Administrators group
