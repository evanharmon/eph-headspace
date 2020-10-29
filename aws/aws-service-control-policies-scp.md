# AWS SERVICE CONTROL POLICIES

## Summary

Notes on AWS SCPs

## Resources

- [Example Policies](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps_examples.html#examples_general)
- [VPC Example Policies](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps_examples.html#examples_vpc)

### VPCs

#### Prevent New Internet Access

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Deny",
      "Action": [
        "ec2:AttachInternetGateway",
        "ec2:CreateInternetGateway",
        "ec2:CreateEgressOnlyInternetGateway",
        "ec2:CreateVpcPeeringConnection",
        "ec2:AcceptVpcPeeringConnection",
        "globalaccelerator:Create*",
        "globalaccelerator:Update*"
      ],
      "Resource": "*"
    }
  ]
}
```
