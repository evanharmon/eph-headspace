# AWS COGNITO IDENTITY CLI

## Summary

Notes on using the `aws cognito-idp` cli for AWS Cognito User Pools Identity Provider service

## Resources

### Roles

#### Create Unauthorized Role

```console
aws iam create-role \
  --role-name hss-auth-unauthorized \
  --assume-role-policy-document file://policies/cognito-unauthorized-trust.json
```

#### Create Authorized Role

```console
aws iam create-role \
  --role-name hss-auth-authorized \
  --assume-role-policy-document file://policies/cognito-authorized-trust.json
```

### Users

#### Admin Create User Shortcut

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

#### Admin User Global Sign Out

Sign out user from ALL devices. Invalidates all refresh tokens.

```console
aws cognito-idp admin-user-global-sign-out \
  --user-pool-id us-east-1_aaaaaaaaa \
  --username myusername
```

#### List Users With Filter

```console
aws cognito-idp list-users \
  --user-pool-id us-east-1_aaaaaaaaa \
  --filter 'email = "evan@email.com"'
```

#### List Users By Sub

```console
aws cognito-idp list-users \
  --user-pool-id us-east-1_aaaaaaaaa \
  --filter 'sub = "1234"'
```

#### List Users And Filter By Domain Name

```console
aws cognito-idp list-users \
  --user-pool-id us-east-1_aaaaaaaaa |\
  jq '.Users[]|select(.Attributes[]|.Value | endswith("@google.com"))'
```

#### List Users In Group

```console
aws cognito-idp list-users-in-group \
  --user-pool-id us-east-1_aaaaaaaaa \
  --group-name mygroup
```

#### Disable User

```console
aws cognito-idp admin-disable-user \
  --user-pool-id us-east-1_aaaaaaaaa \
  --username "Facebook_111111111111111"
```

#### Delete User

user must be disabled

```console
aws cognito-idp admin-delete-user \
  --user-pool-id us-east-1_aaaaaaaaa \
  --username "Facebook_111111111111111"
```

#### Update User Attributes

```console
aws cognito-idp admin-update-user-attributes \
  --user-pool-id us-east-1_aaaaaaaaa \
  --username "Facebook_111111111111111" \
  --user-attributes Name="custom:CustomAttr1",Value="Purple"
```

#### Delete User Attributes

```console
aws cognito-idp admin-delete-user-attributes \
  --user-pool-id us-east-1_aaaaaaaaa \
  --username "Facebook_111111111111111" \
  --user-attribute-names "custom:CustomAttr1"
```

### Identities

#### Remove Linked Identity

```console
aws cognito-idp admin-disable-provider-for-user \
  --user-pool-id us-east-1_aaaaaaaaa \
  --user "ProviderName=Facebook,ProviderAttributeName=Cognito_Subject,ProviderAttributeValue=111111111111111"
```

### Identity Providers

#### Describe Identity Provider

Provider name for apple is [SignInWithApple](https://docs.aws.amazon.com/cli/latest/reference/cognito-idp/describe-identity-provider.html)

```console
aws cognito-idp describe-identity-provider \
  --user-pool-id=us-east-1_AAAAAAAAA \
  --provider-name=SignInWithApple
```
