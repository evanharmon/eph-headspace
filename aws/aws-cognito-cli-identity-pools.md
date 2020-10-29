# AWS COGNITO IDENTITY CLI

## Summary

Notes on using the `aws cognito-identity` cli for AWS Cognito Federated
Identities service. Identity Pools.

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

## Unlink Identity

Cognito User Group identity example:

cli-input.json

```json
{
  "IdentityId": "us-east-1:eeeeeeee-cccc-7777-8888-cccccccccccc",
  "Logins": {
    "cognito-idp.us-east-1.amazonaws.com/us-east-1_AAAAAAAAA": "ID_TOKEN"
  },
  "LoginsToRemove": ["cognito-idp.us-east-1.amazonaws.com/us-east-1_AAAAAAAAA"]
}
```

```console
aws cognito-identity unlink-identity --cli-input-json file://cli-input.json
```
