# AWS ECS CAPACITY PROVIDERS

## Summary

Notes on scaling ECS with capacity providers

## Resources

- [AWS ECS Capacity Provider Docs](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/cluster-capacity-providers.html)
- [AWS Blog Capacity Providers](https://aws.amazon.com/blogs/containers/deep-dive-on-amazon-ecs-cluster-auto-scaling/)
- [AWS Capacity Providers Workshop](https://ec2spotworkshops.com/ecs-spot-capacity-providers/module-2/add_fargate_cp.html)
- [Medium Plain English Walkthrough Scaling ECS](https://aws.plainenglish.io/auto-scaling-aws-ecs-service-with-our-own-cluster-capacity-provider-84f4b64a69ff)
- [AWS Youtube Video Walkthrough](https://www.youtube.com/watch?v=Vb_4wAEcfpQ)

## Base & Weight Explained

The base value designates how many tasks, at a minimum, to run on the specified capacity provider.
Only one capacity provider in a capacity provider strategy can have a base defined.

In a capacity provider strategy, only one capacity provider can have a base value defined. If no base value is specified, the default value of 0 is used.

Capacity Provider (CP)
Example:

```
CP1: base=3, weight=1
CP2: base=0, weight=1
```

CP1 starts with 4 total tasks
CP2 starts with 1 total tasks

Scale Out (Scale up # of instances) follows weight of 1

CP1 adds 1 task
CP2 adds 1 task
