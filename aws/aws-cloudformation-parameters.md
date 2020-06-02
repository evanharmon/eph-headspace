# AWS CLOUDFORMATION PARAMETERS
[AWS Blog Examples]
(https://aws.amazon.com/blogs/devops/using-the-new-cloudformation-parameter-types/)

## List
String – A literal string
Number – An integer or float
List<Number> – An array of integers or floats
CommaDelimitedList – An array of literal strings that are separated by commas
AWS::EC2::KeyPair::KeyName – An Amazon EC2 key pair name
AWS::EC2::SecurityGroup::Id – A security group ID
AWS::EC2::Subnet::Id – A subnet ID
AWS::EC2::VPC::Id – A VPC ID
List<AWS::EC2::VPC::Id> – An array of VPC IDs
List<AWS::EC2::SecurityGroup::Id> – An array of security group IDs
List<AWS::EC2::Subnet::Id> – An array of subnet IDs

## Selection List
```
  Environment:
    Default: Development
    Type: String
    AllowedValues:
      - Development
      - Production
```

## Comma-Delimited-List
```
Parameters:
  DbSubnetIpBlocks:
    Description: "Comma-delimited list of three CIDR blocks"
    Type: CommaDelimitedList
    Default: "10.0.48.0/24, 10.0.112.0/24, 10.0.176.0/24"
```

## IPv4 /26 CIDR Block
```
AllowedPattern: ^(([0-9]|[1-9][0-9]|1[0-9]{2}|2[0-4][0-9]|25[0-5])).(([0-9]|[1-9][0-9]|1[0-9]{2}|2[0-4][0-9]|25[0-5])).(([0-9]|[1-9][0-9]|1[0-9]{2}|2[0-4][0-9]|25[0-5])).([0]|[6][4]|[1][2][8])/26$
```
