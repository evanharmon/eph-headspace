# DOCKER GENERAL

## Summary

Notes on docker

## Login To AWS ECR

MAC OS X

```console
echo "$(aws ecr get-authorization-token | \
  jq -r '.authorizationData[].authorizationToken' | \
  base64 -D | cut -d: -f2)" | \
  docker login -u AWS \
    "https://$(aws sts get-caller-identity --query Account --output text).dkr.ecr.$AWS_DEFAULT_REGION.amazonaws.com/$ECR_REPO" \
    --password-stdin
```

LINUX

```console
echo "$(aws ecr get-authorization-token | \
  jq -r '.authorizationData[].authorizationToken' | \
  base64 -d | cut -d: -f2)" | \
  docker login -u AWS \
    "https://$AWS_ACCOUNT_ID.dkr.ecr.$AWS_DEFAULT_REGION.amazonaws.com/$ECR_REPO" \
    --password-stdin
```

ON EC2

```console
export AWS_ACCOUNT_ID="$(aws sts get-caller-identity --query Account --output text)"
export AWS_DEFAULT_REGION='us-east-1'
sudo echo "$(aws ecr get-authorization-token | \
  sudo jq -r '.authorizationData[].authorizationToken' | \
  sudo base64 -d | sudo cut -d: -f2)" | \
  sudo docker login -u AWS \
    "https://$AWS_ACCOUNT_ID.dkr.ecr.$AWS_DEFAULT_REGION.amazonaws.com/$ECR_REPO" \
    --password-stdin
```

afterwards delete creds

```console
rm -rf /root/.docker/config.json
```

## Copy Localhost File to Docker Container

```console
docker cp filename 732e4ffd08fe:/home/dev/filename
```

## Copy container file to localhost

```console
docker cp 732e4ffd08fe:/home/dev/filename filename
```

## Set Hostname at run

```console
docker run -it -h nvim --name nvim evanharmon/hss-base-nvim:ubuntu zsh
```

## Save Time Docker Files

run as one line to speed it up

## Search for container by name

```console
docker ps --filter "name=nvim"
```

## View Container Logs

```console
docker logs <container name>
```

## View log of Docker

```console
systemctl status docker
```

## Mac docker.sock

located at `/private/var/run/docker.sock`
