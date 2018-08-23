# AWS IAM CLI

## Create Role
```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "mobileanalytics:PutEvents",
        "cognito-sync:*"
      ],
      "Resource": [
        "*"
      ]
    }
  ]
}
```

```
$ aws iam create-role \
    --role-name hss-auth-unauthorized \
    --assume-role-policy-document file://policies/cognito-unauthorized-trust.json
```

# Attach An Inline Role Policy
```
$ aws iam put-role-policy \
    --role-name hss-auth-unauthorized \
    --policy-name unauthorized \
    --policy-document file://policies/cognito-unauthorized.json
```

# Attach Role Policy
```
$ aws iam attach-role-policy \
    --policy-arn arn:aws:iam::aws:policy/ReadOnlyAccess \
    --role-name LimitCheckRole
```
