# AWS CLOUDFORMATION OUTPUTS

## Use
declares values to be used in cross-stack references
viewable in CloudFormation console

## LIMITS
60 Parameters
60 Outputs

## GetAtt workaround
GetAtt and ImportValue can't work together - export every property you need
```
  TransientVPC:
    Description: Transient VPC
    Value: !Ref TransientVPC
    Export:
      Name: !Sub "${AWS::StackName}-TransientVPCID"
  TransientVPCDefaultNetworkAcl:
    Description: Transient VPC Default Network ACL
    Value: !Get Att TransientVPC.DefaultNetworkAcl
    Export:
      Name: !Sub "${AWS::StackName}-TransientVPCDefaultNetworkAcl"
```
