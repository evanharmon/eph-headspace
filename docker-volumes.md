# DOCKER VOLUMES

## Summary

Notes on using docker volumes with the docker CLI

## Mount Volume On Docker Run

```console
docker run -v `pwd`:`pwd` -w `pwd` -i -t ubuntu pwd
docker run --read-only -v /User/me/.aws:/home/ec2-user/.aws -i -t ubuntu pwd
```

## Mount S3 As A Volume

[AWS Blog Post EBS](https://aws.amazon.com/blogs/compute/amazon-ecs-and-docker-volume-drivers-amazon-ebs/)
[SO ECS Volume](https://stackoverflow.com/questions/52041550/mount-s3-bucket-as-filesystem-on-aws-ecs-container)
