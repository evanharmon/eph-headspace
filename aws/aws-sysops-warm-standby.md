# AWS SYSOPS WARM STANDBY
scaled-down version of a fully functional environment always running in the
cloud

## Additional Uses
Testing, qa, non prod workloads

## Preparation Phase
- setup ec2 instances to mirror or replicate data
- create and maintain AMIs
- run your applications on minimum footprint architecture
- patch and update software and config files

## Recovery Phase
- horizontally scale ec2 instances in fleet with load balancer
- vertically scale app to larger ec2 instances as needed
- manually change DNS or use route53 health checks
- add resilience or scale up databases

## Possible Improvements
- consider using auto scaling to right size fleet
