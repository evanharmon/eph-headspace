# AWS ECS

## Summary

Notes on working with ECS in AWS

## Resources

[GH Awesome](https://github.com/nathanpeck/awesome-ecs)
[AWS Local Dev Blog](https://aws.amazon.com/blogs/compute/a-guide-to-locally-testing-containers-with-amazon-ecs-local-endpoints-and-docker-compose/)
[GH Local Dev Repo](https://github.com/awslabs/amazon-ecs-local-container-endpoints<Paste>)
[Private ECS Fargate](https://aws.amazon.com/blogs/compute/access-private-applications-on-aws-fargate-using-amazon-api-gateway-privatelink/)

## Log File Locations

[AWS DOC](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/logs.html)

## Minimum / Maximum Percent

[SO Explanation](https://stackoverflow.com/questions/40731143/what-is-the-minimum-healthy-percent-and-maximum-percent-in-amazon-ecs)

More confusing than you think.

```
If you want to make sure there is always at least 1 task running you need to
set desired to 1, minimum to 100% and maximum to 200%
```
