# AWS CLOUDFORMATION GOTCHAS

## DependsOn VPC-Gateway Attachment
Auto Scaling groups
Amazon EC2 instances
Elastic Load Balancing load balancers
Elastic IP addresses
Amazon RDS database instances
Amazon VPC routes that include the Internet gateway

## EC2::Route
can only have one of: GatewayId, InstanceId, NatGatewayId, NetworkInteraceId,
or VpcPeeringConnectionId

## EC2::SecurityGroup
Can't use `!Ref` linking two groups to each other as it's a circular dependency.
Use this:
```
Fn::GetAtt:
  - TargetSG
  - GroupId
```

## Error: Unresolved Resource Dependencies
Check for a mispelled property name such as VcpId when it should be VpcId

## EIP
domain must be 'vpc' lowercase
`domain: "vpc"`

## Role Refs in Instances
need DependsOn

## RoleNames
need to be unique across account - prepend region to be safe

## Error: Route Table and Gateway not on same network/vpc
Each Subnet needs to have its own separate route table
Might need `DependsOn: AttachGateway`

## SecurityGroupIds
Do not use this property if `NetworkInterfaces` is specified

## Error: Parameter groupName cannot be used with the parameter subnet
When not using a NetworkInterface on an instance, use the `SecurityGroupIds`
parameter intead of `SecurityGroup`

## Export Names
must be unique within a region

## Autoscaling and Updates
does not update current resources unless you set `UpdatePolicy`

## Autoscaling and ELBs
(http://docs.aws.amazon.com/autoscaling/latest/userguide/attach-load-balancer-asg.html)
Don't register instances with load balancer or target group. Auto scaling does
this when it launches the load balancder or target group

Don't use `LoadBalancerNames` property for App ELBs! Use TargetGroupARNs instead

## Subnet stuck on 'CREATING'
Make sure CidrBlock isn't using double 00's. ie 10.146.4.00/26

## CLI Multiple Parameters
```
$ aws create-stack \
    --parameters ParameterKey=subnet1AZ,ParameterValue=us-east-2a ParameterKey=subnet2AZ, ParameterValue=us-east-2b ParameterKey=subnet3AZ,ParameterValue=us-east-2c
```

## DBSecurityGroups
needs vpc id and sg name NOT regular ref id
```
  DBSecurityGroup:
    Type: AWS::RDS::DBSecurityGroup
    Properties:
      EC2VpcId: !Ref VPC
      GroupDescription: WebServer Access
      DBSecurityGroupIngress:
        EC2SecurityGroupId: !GetAtt PublicSecurityGroup.GroupId
```

## Tcp Security Group Ingress/Egress All Ports
"-1" will not work in FromPort/ToPort
```
IpProtocol: tcp
FromPort: 0
ToPort: 65535
CidrIp: 0.0.0.0/0
```

## Fn::ImportValue must not depend on any resources, imported values, or Fn::GetAZs
Make sure you are using SecurityGroupIds and not SecurityGroups
Look at your `${TeamName}` style !Sub references to check for a mispelling

## UserData with line breaks
```
UserData:
    Fn::Base64: !Sub |
        #!/bin/bash -xe
        yum update -y
```

## Lambda code in a Zipfile
> can combine some lines together - | forces new lines
```
Code:
    ZipFile: |
```

## AutoScaling Group Tags require extra property
```
Key: String
Value: String
PropagateAtLaunch: Boolean
```

## Autoscaling group hanging on 'create in progress'
Make sure security groups per instance is 5 or less

## Policy failed legacy parsing
Make sure you aren't using a reference like `${VPCID}` and forgetting to
surround it with `!Sub ""`

## Route53 ResourceRecordSet 'invalid request' error
If on alias record, make sure target has TTL supplied

## Second instance init userdata not working
Cannot use the same `AWS::CloudFormation::Init:` in multiple places in a
cloudformation template. You have to change some values so they are not
identical configs

## Template bucket referenced does not exist - s3 url
need to use this format
```
aws cloudformation create-stack \
    --stack-name test \
    --template-url https://s3-west-2.amazonaws.com/bucket/template.yaml
```

## Aurora requires DBCluster
DBInstance uses property
`VPCSecurityGroups`
DBCluster uses property
`VPCSecurityGroupIds`
