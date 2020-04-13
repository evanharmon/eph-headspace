# AWS COGNITO IDP CLI

## Summary

Notes on using the `aws cognito-identity` cli for AWS Cognito Federated Identities service

## Create New Pool

```console
aws cognito-identity create-identity-pool \
  --identity-pool-name hssauth \
  --allow-unauthenticated-identities \
  --supported-login-providers KeyName1=accounts.google.com
```

## Create Unauthorized Role

```console
aws iam create-role \
  --role-name hss-auth-unauthorized \
  --assume-role-policy-document file://policies/cognito-unauthorized-trust.json
```

## Create Authorized Role

```console
aws iam create-role \
  --role-name hss-auth-authorized \
  --assume-role-policy-document file://policies/cognito-authorized-trust.json
```
