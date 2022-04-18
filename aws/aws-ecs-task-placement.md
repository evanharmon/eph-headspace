# AWS ECS TASK PLACEMENT

## Summary
Notes on ecs task placement constraints and strategies

## Resources
- [AWS Docs](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task-placement.html)
- [AWS Blog Task Placement](https://aws.amazon.com/blogs/compute/amazon-ecs-task-placement/)

## ECS Default Strategy
spreads tasks across availability zones and instances

## DistinctInstance Constraint
`The distinctInstance constraint never places multiple copies of a task on a single instance`
