# AWS IAM CLOUDFORMATION EXAMPLES

## Example 1:
Policy attached to Role, Role attached to Instance Profile
```
AppServerInstanceProfile:
   DependsOn: "AppServerRole"
   Type: "AWS::IAM::InstanceProfile"
   Properties:
     Path: "/"
     Roles:
       - Ref: "AppServerRole"

AppServerRole:
   Type: "AWS::IAM::Role"
   Properties:
     AssumeRolePolicyDocument:
       Version: "2012-10-17"
       Statement:
         - Effect: "Allow"
           Principal:
             Service:
               - "ec2.amazonaws.com"
           Action:
             - "sts:AssumeRole"
     Path: "/"
```

# Example Managed Policy
```
CreateTestDBPolicy:
  Type: "AWS::IAM::ManagedPolicy"
  Properties:
    Description: "Policy for creating a test database"
    Path: "/"
    PolicyDocument:
      Version: "2012-10-17"
      Statement:
        -
          Effect: "Allow"
          Action: "rds:CreateDBInstance"
          Resource:
            Fn::Join:
              - ""
              -
                - "arn:aws:rds:"
                -
                  Ref: "AWS::Region"
                - ":"
                -
                  Ref: "AWS::AccountId"
                - ":db:test*"
          Condition:
            StringEquals:
              rds:DatabaseEngine: "mysql"
        -
          Effect: "Allow"
          Action: "rds:CreateDBInstance"
          Resource:
            Fn::Join:
              - ""
              -
                - "arn:aws:rds:"
                -
                  Ref: "AWS::Region"
                - ":"
                -
                  Ref: "AWS::Region"
                - ":db:test*"
          Condition:
            StringEquals:
              rds:DatabaseClass: "db.t2.micro"
    Groups:
      - "TestDBGroup"
```

# Example Role with Embedded Policy
```
AWSTemplateFormatVersion: "2010-09-09"
Resources:
  RootRole:
    Type: "AWS::IAM::Role"
    Properties:
      AssumeRolePolicyDocument:
        Version: "2012-10-17"
        Statement:
          -
            Effect: "Allow"
            Principal:
              Service:
                - "ec2.amazonaws.com"
            Action:
              - "sts:AssumeRole"
      Path: "/"
      Policies:
        -
          PolicyName: "root"
          PolicyDocument:
            Version: "2012-10-17"
            Statement:
              -
                Effect: "Allow"
                Action: "*"
                Resource: "*"
  RootInstanceProfile:
    Type: "AWS::IAM::InstanceProfile"
    Properties:
      Path: "/"
      Roles:
        -
          Ref: "RootRole"
```

# Example Role with External Policy
```
AWSTemplateFormatVersion: "2010-09-09"
Resources:
  RootRole:
    Type: "AWS::IAM::Role"
    Properties:
      AssumeRolePolicyDocument:
        Version: "2012-10-17"
        Statement:
          -
            Effect: "Allow"
            Principal:
              Service:
                - "ec2.amazonaws.com"
            Action:
              - "sts:AssumeRole"
      Path: "/"
  RolePolicies:
    Type: "AWS::IAM::Policy"
    Properties:
      PolicyName: "root"
      PolicyDocument:
        Version: "2012-10-17"
        Statement:
          -
            Effect: "Allow"
            Action: "*"
            Resource: "*"
      Roles:
        -
          Ref: "RootRole"
  RootInstanceProfile:
    Type: "AWS::IAM::InstanceProfile"
    Properties:
      Path: "/"
      Roles:
        -
          Ref: "RootRole"
```
