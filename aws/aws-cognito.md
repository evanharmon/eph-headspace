# AWS COGNITO

## Summary

Notes on working with AWS Cognito services

## Resources

- [Passwordless Email Authentication](https://aws.amazon.com/blogs/mobile/implementing-passwordless-email-authentication-with-amazon-cognito/)
- [OAuth 2.0 Grants](https://aws.amazon.com/blogs/mobile/understanding-amazon-cognito-user-pool-oauth-2-0-grants/)
- [Role-Based Access Control](https://docs.aws.amazon.com/cognito/latest/developerguide/role-based-access-control.html)
- [Developer Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/google.html)
- [Auth Flow](https://docs.aws.amazon.com/cognito/latest/developerguide/authentication-flow.html)
- [Link Multiple Accounts Same Email](https://forums.aws.amazon.com/thread.jspa?threadID=261470)

## User Pools

#### Multiple Account / Identities

- [Link Existing User Account With Identity From External Provider](https://docs.aws.amazon.com/cognito-user-identity-pools/latest/APIReference/API_AdminLinkProviderForUser.html)

#### User Pool Setup

- create sms role if you want sms
- if using email, create SES verified identity. Log in to email to verify

## Identity Pools

Each unauthenticated user has a unique identity in the identity pool, even though they haven't been individually logged in and authenticated.

## Server Side Token Check

Cognito Identity Pools DO NOT check against the user pool by default. This
means a user can be disabled / deleted in the User Pool and their identity pool
authorization creds will STILL WORK.

#### Turn On Server Side Token Check

```console
aws cognito-identity update-identity-pool \
  --identity-pool-id \
  --identity-pool-name \
  --allow-unauthenticated-identities \
  --cognito-identity-providers ProviderName=,ClientId=,ServerSideTokenCheck=<true|false>
```

#### Mobile Setup NOTE!!

If your app uses Google and will be available on multiple mobile platforms,
you should configure it as an OpenID Connect Provider, adding all created
client IDs as additional audience values to allow for better integration. To
learn more about Google's cross-client identity model, see Cross-client
Identity.

#### Identity Pool Setup

- create identity pool
- create authorized and unauthorized roles, with policies and trusts

## Policies

### Policy Conditions

`cognito-identity.amazonaws.com:amr` contains more text than authentication
status. Use `ForAnyValue:StringLike` to match only the
authentication status

```json
{
  "ForAnyValue:StringLike": {
    "cognito-identity.amazonaws.com:amr": "unauthenticated"
  }
}
```

### Policy Examples

#### Basic Unauthorized Role Policy

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

#### Basic Unauthorized Role Trust Relationship

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Federated": "cognito-identity.amazonaws.com"
      },
      "Action": "sts:AssumeRoleWithWebIdentity",
      "Condition": {
        "StringEquals": {
          "cognito-identity.amazonaws.com:aud": "us-west-2:eeeeeeee-eeee-eeee-eeee-eeeeeeeeeeee"
        },
        "ForAnyValue:StringLike": {
          "cognito-identity.amazonaws.com:amr": "unauthenticated"
        }
      }
    }
  ]
}
```

#### Basic Authorized Role Policy

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "mobileanalytics:PutEvents",
        "cognito-sync:*",
        "cognito-identity:*"
      ],
      "Resource": ["*"]
    }
  ]
}
```

#### Basic Unauthorized Role Trust Relationship

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Federated": "cognito-identity.amazonaws.com"
      },
      "Action": "sts:AssumeRoleWithWebIdentity",
      "Condition": {
        "StringEquals": {
          "cognito-identity.amazonaws.com:aud": "us-west-2:eeeeeeee-eeee-eeee-eeee-eeeeeeeeeeee"
        },
        "ForAnyValue:StringLike": {
          "cognito-identity.amazonaws.com:amr": "authenticated"
        }
      }
    }
  ]
}
```
