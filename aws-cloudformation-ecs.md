# AWS CLOUDFORMATION ECS

## ECS Service Creation Does Not Finish
* Make sure CFN success are being sent in instance userdata to autoscaling group
* Make sure `Role` property exists on ECSService if specifying `LoadBalancers`
* Click in to ECS service, view `events` tab. There might be an error on
cpu / mem units available
