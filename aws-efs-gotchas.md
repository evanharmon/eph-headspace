# AWS EFS GOTCHAS

## Can't Resolve When Mounting To EC2 Instance
Make sure VPC has `DNS hostnames: yes` and `DNS resolution: yes`

## Mount Command Hangs On EC2 Instance For EFS
Confirm below security group settings on EC2 instance:
* Inbound port 2049 allowed FROM EFS security group
* Outbound port 2049 allowed TO EFS security group

Confirm below security group settings on EFS:
* Inbound port 2049 allowed FROM EC2 security group

## ECS Read Errors
Give docker user ownership
`sudo chown -R 1000 /efs/jenkins_master`
