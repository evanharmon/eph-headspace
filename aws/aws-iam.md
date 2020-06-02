# AWS IAM

## Summary

Notes on AWS Identity And Access Management

## Policies

- [Action Lists per Service](http://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_actionsconditions.html)
- [Full List](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_actions-resources-contextkeys.html)
- [Policy Evaluation Logic](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_evaluation-logic.html#policies_evaluation_example)

## Best Practices

[AWS](http://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)

- lock away your AWS account (root) access keys
- create individual IAM users
- use groups to assign permissions to IAM users
- grant least privilege
- configure a strong password policy for your users
- enable MFA for privileged users
- use roles for applications that run on Amazon EC2 instances
- delegate by using roles instead of by sharing credentials
- rotate credentials regularly
- remove unnecessary credentials
- use policy conditions for extra security
- monitor activity in your AWS account
- video presentation about IAM best practices

## Roles

Users can explicitly switch roles to perform tasks
Roles are universal - can use across any region
MFA can be added to specific roles

### Trust Policy

Assume a role as an IAM user

example trust relationship policy

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "",
      "Effect": "Allow",
      "Principal": {
        "Service": "codebuild.amazonaws.com"
      },
      "Action": "sts:AssumeRole"
    },
    {
      "Sid": "",
      "Effect": "Allow",
      "Principal": {
        "AWS": ["arn:aws:iam::111111111111:user/myname"]
      },
      "Action": "sts:AssumeRole"
    }
  ]
}
```

### Permissions Policy

allowed actions and resources

## Instance Roles

- provides access key information in output
- more secure than using access keys on instances

```console
$ curl http://169.254.169.254/latest/meta-data/iam/security-credentials/role-name
```

### Assignment

Can only be assigned at instance creation

## Implicit Denial

An implicit denial occurs when there is no applicable Deny statement but also
no applicable Allow statement. Because an IAM user, role, or federated user is
denied access by default, they must be explicitly allowed to perform an action.
Otherwise, they are implicitly denied access.

## Explicit Denial

A request results in an explicit deny if an applicable policy includes a Deny
statement. If policies that apply to a request include an Allow statement and a
Deny statement, the Deny statement trumps the Allow statement. The request is
explicitly denied.
