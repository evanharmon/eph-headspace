# AWS EC2 ECS

## Steps To Create ECS cluster
(https://docs.aws.amazon.com/AmazonECS/latest/developerguide/get-set-up-for-amazon-ecs.html#create-an-iam-role)
1. Create VPC
2. Create Subnet
3. Create Security Group
4. Create Keypair
5. Create IAM Role ecsInstanceRole using EC2 Role for Elastic Container Service,
AmazonEC2ContainerServiceforEC2Role policy
6. Create instance with UserData to join cluster

## UserData To Join Cluster
```
#!/bin/bash
echo ECS_CLUSTER=your_cluster_name >> /etc/ecs/ecs.config
```

## Updating ECS Agent On ECS AMI
(https://docs.aws.amazon.com/AmazonECS/latest/developerguide/agent-update-ecs-ami.html)
```
$ sudo yum update -y ecs-init
$ sudo service docker restart
$ sudo start ecs
```

## Use Cloudwatch AWS Logs
(https://docs.aws.amazon.com/AmazonECS/latest/developerguide/using_cloudwatch_logs.html)
1. Create `ECS-CloudWatchLogs` policy
2. Attach the `ECS-CloudWatchLogs` policy to your `ecsInstanceRole`
3. Install awslogs `$ sudo yum install -y awslogs`
