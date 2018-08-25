# AWS AUTO SCALING CLOUDFORMATION

## GOTCHAS
Do not use property 'LaunchBalancerNames' with V2 App ELBs

## Example
```
---
AWSTemplateFormatVersion: !!str 2010-09-09

Description: Basic Auto Scaling with ELBs

Parameters:
  InstanceType:
    Type: String
    Default: t2.nano
    Description: Instance Type
    AllowedValues:
      - t1.micro
      - t2.nano
      - t2.micro
      - t2.small
      - t2.medium
    ConstraintDescription: must be a valid EC2 instance type
  KeyName:
    Type: AWS::EC2::KeyPair::KeyName
    Description: Name of an existing EC2 KeyPair
    ConstraintDescription: Must be the name of an existing EC2 key pair
  SSHLocation:
    Description: External IPv4 address range for SSH
    Type: String
    MinLength: 9
    MaxLength: 18
    Default: 201.101.18.0/24
    AllowedPattern: "(\\d{1,3})\\.(\\d{1,3})\\.(\\d{1,3})\\.(\\d{1,3})/(\\d{1,2})"
    ConstraintDescription: must be a valid IPv4 CIDR Range

Resources:
  VPC:
    Type: AWS::EC2::VPC
    Properties:
      CidrBlock: 10.0.0.0/16
      EnableDnsHostnames: true
      EnableDnsSupport: true
      InstanceTenancy: default
      Tags:
        - Key: Name
          Value: !Ref AWS::StackName
  AttachGateway:
    DependsOn: InternetGateway
    Type: AWS::EC2::VPCGatewayAttachment
    Properties:
      VpcId: !Ref VPC
      InternetGatewayId: !Ref InternetGateway
  InternetGateway:
    DependsOn: VPC
    Type: AWS::EC2::InternetGateway
    Properties:
      Tags:
        - Key: Name
          Value: AWS::StackName
  PublicSubnet1:
    Type: AWS::EC2::Subnet
    Properties:
      AvailabilityZone: us-east-1b
      VpcId: !Ref VPC
      CidrBlock: 10.0.1.0/24
      Tags:
        - Key: Name
          Value: AWS::StackName
  # Assures IGW and RouteTable are on same network
  PublicSubnet1RouteTable:
    DependsOn: AttachGateway
    Type: AWS::EC2::RouteTable
    Properties:
      VpcId: !Ref VPC
      Tags:
        - Key: Name
          Value: AWS::StackName
  PublicSubnet1RouteTableAssociation:
    Type: AWS::EC2::SubnetRouteTableAssociation
    Properties:
      SubnetId: !Ref PublicSubnet1
      RouteTableId: !Ref PublicSubnet1RouteTable
  # Assures IGW and RouteTable are on same network
  PublicSubnet1InternetRoute:
    DependsOn:
      - AttachGateway
      - InternetGateway
    Type: AWS::EC2::Route
    Properties:
      DestinationCidrBlock: 0.0.0.0/0
      GatewayId: !Ref InternetGateway
      RouteTableId: !Ref PublicSubnet1RouteTable

  PublicSubnet2:
    Type: AWS::EC2::Subnet
    Properties:
      AvailabilityZone: us-east-1c
      VpcId: !Ref VPC
      CidrBlock: 10.0.2.0/24
      Tags:
        - Key: Name
          Value: AWS::StackName
  # Assures IGW and RouteTable are on same network
  PublicSubnet2RouteTable:
    DependsOn: AttachGateway
    Type: AWS::EC2::RouteTable
    Properties:
      VpcId: !Ref VPC
      Tags:
        - Key: Name
          Value: AWS::StackName
  PublicSubnet2RouteTableAssociation:
    Type: AWS::EC2::SubnetRouteTableAssociation
    Properties:
      SubnetId: !Ref PublicSubnet2
      RouteTableId: !Ref PublicSubnet2RouteTable
  # Assures IGW and RouteTable are on same network
  PublicSubnet2InternetRoute:
    Type: AWS::EC2::Route
    Properties:
      DestinationCidrBlock: 0.0.0.0/0
      GatewayId: !Ref InternetGateway
      RouteTableId: !Ref PublicSubnet2RouteTable

  EIP:
    Type: AWS::EC2::EIP
    Properties:
      Domain: vpc

  AppLoadBalancer:
    Type: AWS::ElasticLoadBalancingV2::LoadBalancer
    Properties:
      Name: !Ref AWS::StackName
      Scheme: internet-facing
      Subnets:
        - !Ref PublicSubnet1
        - !Ref PublicSubnet2
      SecurityGroups:
        - !Ref PublicSecurityGroup
  ALBListener:
    Type: AWS::ElasticLoadBalancingV2::Listener
    Properties:
      DefaultActions:
        - Type: forward
          TargetGroupArn: !Ref ALBTargetGroup
      LoadBalancerArn: !Ref AppLoadBalancer
      Port: 80
      Protocol: HTTP
  # Targets added via Auto Scaling Group
  ALBTargetGroup:
    Type: AWS::ElasticLoadBalancingV2::TargetGroup
    Properties:
      HealthCheckIntervalSeconds: 10
      HealthCheckPath: /healthcheck.html
      HealthCheckPort: 80
      HealthCheckProtocol: HTTP
      HealthCheckTimeoutSeconds: 5
      HealthyThresholdCount: 3
      Name: alb-target-group
      Port: 80
      Protocol: HTTP
      UnhealthyThresholdCount: 2
      VpcId: !Ref VPC
  # Do not use property 'LaunchBalancerNames' with V2 App ELBs
  AutoScalingGroup1:
    DependsOn:
      - AttachGateway
    Type: AWS::AutoScaling::AutoScalingGroup
    Properties:
      VPCZoneIdentifier:
        - !Ref PublicSubnet1
        - !Ref PublicSubnet2
      MinSize: 2
      MaxSize: 5
      HealthCheckType: ELB
      HealthCheckGracePeriod: 120
      DesiredCapacity: 2
      LaunchConfigurationName: !Ref LaunchConfig
      TargetGroupARNs:
        - !Ref ALBTargetGroup
  LaunchConfig:
    DependsOn:
      - PublicSubnet1
    Type: AWS::AutoScaling::LaunchConfiguration
    Metadata:
      Comment1: Install and start up httpd with healthcheck file
      AWS::CloudFormation::Init:
        config:
          packages:
            yum:
              httpd: []
          files:
            /var/www/html/healthcheck.html:
              content: health check completed
              mode: !!str 000644
              owner: root
              group: root
          services:
            sysvinit:
              httpd:
                enabled: true
                ensureRunning: true
                files:
                  - /var/www/healthcheck.html
    Properties:
      AssociatePublicIpAddress: true
      InstanceType: !Ref InstanceType
      ImageId: ami-c481fad3
      KeyName: !Ref KeyName
      SecurityGroups:
        - !Ref PublicSecurityGroup
      UserData:
        Fn::Base64:
          !Sub |
            #!/bin/bash -xe
            yum update -y
            /opt/aws/bin/cfn-init -v -s ${AWS::StackName} -r LaunchConfig --region ${AWS::Region}
  PublicSecurityGroup:
    Type: AWS::EC2::SecurityGroup
    Properties:
      VpcId: !Ref VPC
      GroupDescription: Allow SSH Access
      SecurityGroupIngress:
        - IpProtocol: tcp
          FromPort: 22
          ToPort: 22
          CidrIp: !Ref SSHLocation
        - IpProtocol: tcp
          FromPort: 80
          ToPort: 80
          CidrIp: 0.0.0.0/0
        - IpProtocol: tcp
          FromPort: 443
          ToPort: 443
          CidrIp: 0.0.0.0/0
      SecurityGroupEgress:
        - IpProtocol: tcp
          FromPort: 80
          ToPort: 80
          CidrIp: 0.0.0.0/0
        - IpProtocol: tcp
          FromPort: 443
          ToPort: 443
          CidrIp: 0.0.0.0/0

Outputs:
  ELBname:
    Description: ELB url
    Value: !GetAtt AppLoadBalancer.DNSName
```
