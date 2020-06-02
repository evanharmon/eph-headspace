# AWS SECURITY PILLAR

## Design Principles
Apply security at all layers
Enable traceability
Automate responses to security events
Focus on securing your system (shared responsibility model)
Automate security best practices

## Definitions
Data Protection
Privilege Management
Infrastructure Protection
Detective controls

## Data Protection Key Services
encrypt data in transit and at rest using: ELB, EBS, S3, & RDS

## Privilege Management Key Services
IAM
MFA

## Infrastructure Protection Key Services
VPC

## Detective Controls Key Services
CloudWatch
CloudTrail
AWS Config

## Best Practices

### Data Movement Between Regions
AWS never initiates movement of Data between regions. Customer does this by
enabling features/leverage services
classify data in to different segments such as:
- public
- limited persons in organization, etc
least privilege access system
Encrypt everything where possible (at rest and/or in transit)
Versioning

### Data Protection Questions
How are you encrypting and protecting data at rest?
How are you encrypting and protecting data in transit (SSL)

### Practices Privilege Management
Access Control Lists (ACLs)
Role Based Accessed Controls
Password Management (password rotation policies)

### Practices Privilege Management Questions
How are you protecting access to and use of the AWS Root account creds?
How are you defining roles and responsibilities of system users to control human
access to the AWS management console and APIs?
How are you limiting automated access (such as from applications, scripts, or
third-party tools/svcs) to AWS resources?
How are you managing keys and credentials?

### Infrastructure Protection
How are you protecting your VPC?
What Security Groups are in place?
What ACLs are in place?
How are you doing routing? (public vs private subnets)

### Infrastructure Protection Questions
How are you enforcing network (Public vs Private subnets) and host-level
boundary protection?
How are you enforcing AWS service level protection? (Groups, MFA,
Password Policy, etc)
How are you protecting the integrity of the operating systems on your EC2
instances?

### Detective Controls
## Detect or identify a security breach
CloudTrail
CloudWatch
AWS Config
S3
Glacier

### Detective Control Questions
How are you capturing and analyzing AWS Logs?
Is CloudTrail turned on in every region?
