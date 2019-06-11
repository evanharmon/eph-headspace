# AWS ECS GOTCHAS

## error: configured logging driver does not support reading"
(https://docs.aws.amazon.com/AmazonECS/latest/developerguide/using_cloudwatch_logs.html)
Check the following to confirm necessary steps are done:
* created the `ecsInstanceRole`
* created the `ECS-CloudWatchLogs` policy and attached to `ecsInstanceRole`
* created the necessary cloudwatch log stream
* installed `sudo yum install -y awslogs jq`
* setup the cloudwatch logs config at `/etc/awslogs/awslogs.conf`
* configured default region at `/etc/awslogs/awscli.conf`
* started agent `sudo service awslogs start`
