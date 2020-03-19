# AWS ECS AGENT

## Summary

Notes on using the ecs agent on ec2

## Resources

- [Using Cloudwatch Logs On ECS](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/using_cloudwatch_logs.html)

### Updating ECS Agent On ECS AMI

amazon linux 1

```console
sudo yum update -y ecs-init
sudo service docker restart
sudo start ecs
```

amazon linux 2

```console
sudo yum update -y ecs-init
sudo systemctl restart docker
sudo systemctl restart ecs
```

### Use Cloudwatch AWS Logs

1. Create `ECS-CloudWatchLogs` policy
2. Attach the `ECS-CloudWatchLogs` policy to your `ecsInstanceRole`
3. Install awslogs `$ sudo yum install -y awslogs`

### Verbose Agent logging

amazon linux 1

```console
export ECS_LOGLEVEL=debug
sudo service docker restart
sudo start ecs
```

amazon linux 2

```console
export ECS_LOGLEVEL=debug
sudo systemctl restart docker
sudo -E systemctl restart ecs
```

### Get ECS Agent Config

```console
curl -s http://localhost:51678/v1/metadata | python -mjson.tool
```

### Debugging

##### Manually Pull Image On EC2 Instance

```console
sudo docker pull 111111111111.dkr.ecr.us-east-1.amazonaws.com/my-repo-name/app/base
```

#### Manually Run Image And Detach

```console
sudo docker run -d -p 8080:8080 \
  025895883795.dkr.ecr.us-east-1.amazonaws.com/go-spire-api/app/base:latest
```
