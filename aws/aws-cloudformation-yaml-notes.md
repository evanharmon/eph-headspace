# AWS CLOUDFORMATION YAML NOTES

## UserData Bash Script Base64 and Sub
one of the intrinsic functions has to be the full version and not the ! short form
```
UserData:
  Fn::Base64:
    !Sub |
      #!/bin/bash -xe
      yum update -y
      /opt/aws/bin/cfn-init -v -s ${AWS::StackName} -r PublicInstance --region ${AWS::Region}
```

## Init File content
```
Files:
  /etc/yum.repos.d/:
    content: !Sub |
      [logstash-2.4]
      name=Logstash repository for 2.4.x packages
      baseurl=https://packages.elastic.co/logstash/2.4/centos
      gpgcheck=1
      gpgkey=https://packages.elastic.co/GPG-KEY-elasticsearch
      enabled=1
```

## Sub with Refs
```
Name: !Sub
  - www.${Domain}
  - { Domain: !Ref RootDomainName }
```

## S3 Example
```
  S3Endpoint:
    Type: AWS::EC2::VPCEndpoint
    Properties:
      PolicyDocument:
        Version: "2012-10-17"
        Statement:
          -
            Effect: "Allow"
            Principal: "*"
            Action:
              - "*"
            Resource:
              - "*"
      RouteTableIds:
        - !Ref rtbprivate1
      ServiceName: !Sub "com.amazonaws.${AWS::Region}.s3"
      VpcId:
        Fn::ImportValue: !Sub "${NetworkStackName}-TransientVPCID"
```

## Get First Availability zone in region
Select from GetAZs function
```
AvailabilityZone:
  Fn::Select:
    - 0
    - Fn::GetAZs: ""
```
