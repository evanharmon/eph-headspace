# AWS AUTO SCALING CLI

## Get List Of Instance Ids
```
$ aws autoscaling describe-auto-scaling-instances \
    --query AutoScalingInstances[].InstanceId
```
