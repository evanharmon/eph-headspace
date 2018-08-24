# AWS CLOUDFORMATION NESTED STACKS

## DependsOn
```
VPCStack:...
SubnetStack:
  DependsOn: VPCStack
```

## Access outputs from another stack
Use the namespace
```
Parameters:
  SubnetAz1: !GetAtt NetworkStack.Outputs.ProdAppSubnetAz1
```

## Pass CommaDelimitedList parameter to child stack
Child Stacks cannot process a List, has to be a string
MyPrivateSubnetCidrBlocks is CommaDelimitedList parameter
```
TransientSubnetStack:
  DependsOn: VPCStack
  Type: AWS::CloudFormation::Stack
  Properties:
    TemplateURL: https://s3.us-east-2.amazonaws.com/...
    Parameters:
      NetworkStackName: !GetAtt VPCStack.Outputs.StackName
      PrivateSubnetCidrBlocks:
        !Join [",", !Ref MyPrivateSubnetCidrBlocks]
```

## Import Value of Outputed Export
```
    Properties:
      VpcId:
        Fn::ImportValue: !Sub "${NetworkStackName}-MyVPCID"
```

## Import Network Stack Name
```
Parameters:
  NetworkStackName:
    Description: Name of the active CloudFormation stack that contains VPC
      resources that will be used in this stack.
    Type: String
    MinLength: 1
    MaxLength: 255
    AllowedPattern: "^[a-zA-Z][-a-zA-Z0-9%]*$"
```

## Export Network Stack Name
```
Outputs:
  StackName:
    Description: Stack Name
    Value: !Ref AWS::StackName
    Export:
      Name: !Sub "AWS::StackName"
```
