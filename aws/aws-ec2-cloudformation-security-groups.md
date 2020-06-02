# AWS EC2 CLOUDFORMATION SECURITY GROUPS

## All Traffic On Ingress Or Egress Objects
`IpProtocol: -1`

## Allow All Traffic Between Members Of A Security Group
```
  AllIngressPrivateSecurityGroup:
    Type: AWS::EC2::SecurityGroupIngress
    Properties:
      GroupId: !Ref PrivateSecurityGroup
      IpProtocol: "-1"
      SourceSecurityGroupId: !Ref PrivateSecurityGroup
      SourceSecurityGroupOwnerId: !Ref AWS::AccountId
```
