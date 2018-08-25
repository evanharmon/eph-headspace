# AWS SYSOPS PILOT LIGHT
Minimal version of environment is always running

## Typical Components
Database servers to replicate data to EC2 or RDS
Prebaked AMIs

## EBS Snapshots
Use to speed up server setup by creating multiple volumes across AZs

## Network Provisioning Strategies
- Pre allocated elastic ip addresses, associate with instances / eni's
- Elastic load balancers - recommended for web apps

## Limitations
Recovery still requires additional configuration and setup to fully deploy apps

## Preparation phase
- Setup EC2 instances to replicate or mirror
- Ensure all custom software and repos are available in AWS
- Create and maintain AMIs of key servers where fast recovery is needed
- Regularly run, test, and apply updates / config changes to servers
- Consider auto provisioning of AWS resources

## Recovery Phase
- Start EC2 instances from AMIs
- Resize existing database / datastore instances to Handle increased traffic
- Add additional database / datastore instances for resilience. For RDS turn on multi AZ
- Change DNS to point to EC2 servers
- Install and configure any non-ami based servers. Prefer automation
