# IAM ROLES

## Summary

## Resources

- [Creating Roles For Web Identity](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_create_for-idp_oidc.html)

### Why Use Roles?

- more secure than storing access key / secret on individual EC2 Instances
- easier to manage
- can only be assigned at EC2 instance provision
- permissions changes to a role happen immediately and affect ones assigned to
  EC2 Instances

### Trust Relationships

#### Example Cognito Trust Relationship

Important for best practices on using cognito and iam roles for apps

Single Condition

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
          "cognito-identity.amazonaws.com:aud": "us-east-1:aaaaaaaa-bbbb-1111-cccc-dddddddddddd"
        }
      }
    }
  ]
}
```

And Condition Multiple StringEquals

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
          "cognito-identity.amazonaws.com:aud": "us-east-1:aaaaaaaa-bbbb-1111-cccc-dddddddddddd"
        }
      }
    },
    {
      "Effect": "Allow",
      "Principal": {
        "Federated": "cognito-identity.amazonaws.com"
      },
      "Action": "sts:AssumeRoleWithWebIdentity",
      "Condition": {
        "StringEquals": {
          "cognito-identity.amazonaws.com:amr": "authenticated"
        }
      }
    }
  ]
}
```
