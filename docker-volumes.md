# DOCKER VOLUMES

## Summary
Notes on using docker volumes with the docker CLI

## Mount Volume On Docker Run
```console
docker run -v `pwd`:`pwd` -w `pwd` -i -t ubuntu pwd
docker run --read-only -v /User/me/.aws:/home/ec2-user/.aws -i -t ubuntu pwd
```
