# AWS IAM CLI

## Create Role

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": ["mobileanalytics:PutEvents", "cognito-sync:*"],
      "Resource": ["*"]
    }
  ]
}
```

```console
aws iam create-role \
  --role-name hss-auth-unauthorized \
  --assume-role-policy-document file://policies/cognito-unauthorized-trust.json
```

# Attach An Inline Role Policy

```console
aws iam put-role-policy \
  --role-name hss-auth-unauthorized \
  --policy-name unauthorized \
  --policy-document file://policies/cognito-unauthorized.json
```

# Attach Role Policy

```console
aws iam attach-role-policy \
  --policy-arn arn:aws:iam::aws:policy/ReadOnlyAccess \
  --role-name LimitCheckRole
```

## Change Password

```console
aws iam update-login-profile \
  --user-name myusername \
  --password "aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa" \
  --no-password-reset-required
```

## Get Account Alias

```console
aws sts list-account-aliases
```
