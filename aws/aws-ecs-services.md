# AWS ECS SERVICES

## Summary

Notes on working with ECS Services in AWS

## Resources
- [SO Minimum and Maximum Healthy Percent](https://stackoverflow.com/questions/40731143/what-is-the-minimum-healthy-percent-and-maximum-percent-in-amazon-ecs)


## Minimum / Maximum Percent
Calculate Minimum: (Minimum / 100) * number_of_tasks
Calculate Maximum: (Maximum / 100) * number_of_tasks

```
Number of Tasks: 2
Minimum Healthy Percent: 0
Maximum Healthy Percent: 200
```

ECS will stop all tasks and re-deploy in one cycle

```
Number of Tasks: 4
Minimum Healthy Percent: 100
Maximum Healthy Percent: 200
```
ECS will not stop any tasks until new tasks are deployed and healthy


