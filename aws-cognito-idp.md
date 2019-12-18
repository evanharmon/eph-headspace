# AWS COGNITO IDENTITY CLI

## Summary

Notes on using the `aws cognito-idp` cli for AWS Cognito User Pools Identity Provider service

## Resources

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

## Admin Create User Shortcut

```console
aws cognito-idp sign-up \
  --client-id 11111111111111111111111111 \
  --username eharmon@gmail.com \
  --password password! \
  --user-attributes Name=email,Value=eharmon@gmail.com

aws cognito-idp admin-confirm-sign-up \
  --user-pool-id us-east-1_aaaaaaaaa \
  --username eharmon@gmail.com

aws cognito-idp admin-update-user-attributes \
  --user-pool-id us-east-1_aaaaaaaaa \
  --username eharmon@gmail.com \
  --user-attributes Name=email_verified,Value=true
```

## Admin User Global Sign Out

Sign out user from ALL devices. Invalidates all refresh tokens.

```console
aws cognito-idp admin-user-global-sign-out \
  --user-pool-id us-east-1_aaaaaaaaa \
  --username myusername
```

## List Users In Group

```console
aws cognito-idp list-users-in-group \
  --user-pool-id us-east-1_aaaaaaaaa \
  --group-name mygroup
```
