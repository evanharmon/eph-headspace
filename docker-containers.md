# DOCKER CONTAINERS

## Summary

Notes on working with docker containers

## List Docker Container Processes

```console
docker ps -a
```

## List PIDs Inside Container

Have to exec in to container

```console
docker exec nvim ps aux
```

## List PIDs Inside Container

Have to exec in to container

```console
docker exec nvim kill 11416
```

## Create Docker Container

```console
docker create --name my-container-name image_name
```

## Run Image

```console
docker run --name my-container-name -d image_name
```

## Start Image and Leave Running

```console
docker run -t -d -p 4984-4985:4984-4985 "couchbase-mobile"
```

## Run Container With Full Color Support

```console
docker run -it -e "TERM=xterm-256color" image_name bash -l
```

## Enter Docker Container As Root

```console
docker exec -u 0 -it mycontainer bash
```

## Remove Stopped Docker Container <hash> (NOT DELETE)

```console
docker rm <hash>
```

## Remove All Running Containers

```console
docker rm -f $(docker ps -aq)
```

## Bash Access

```console
docker exec -it my-container-name bash
```

## Docker Bind Container To Host Port / Expose Port

```console
docker run -d -p 80:3000
```

## Leave Container But Keep It Running

`<ctrl>pq`

## Check Stats On Docker Container

```console
docker stats <UUID>
```

## Check Log

```console
docker logs <UUID>
```

## Check Events

```console
docker events --since 1h
```

## Run Docker Container Without Default Seccomp Profile

Avoids the `could not launch process: fork/exec ...: operation not permitted`
error
[Docs](https://docs.docker.com/engine/security/seccomp/#significant-syscalls-blocked-by-the-default-profile)

```console
docker run --rm -it --security-opt seccomp=unconfined debian:jessie \
    unshare --map-root-user --user sh -c whoami
```

## Mount Folder To Container

[Mount Consistency](https://docs.docker.com/storage/bind-mounts/#configure-mount-consistency-for-macos)
use delegate consistency on MAC OSX to help performance

SSH folder

```console
docker run -it --rm --name nvim \
  --mount type=bind,source="$HOME/.ssh",destination=/root/.ssh,readonly \
  eph-nvim/base:latest
```

Git repo folder

```
PROJECT_DIR="$(basename "$PWD")"; CONTAINER_DIR="/root/code"; \
docker run -it --rm --name nvim \
  --mount type=bind,source="$HOME/.ssh",destination=/root/.ssh,readonly \
  --mount type=bind,source="$(pwd)",destination="$CONTAINER_DIR"/"$PROJECT_DIR",consistency=delegated \
  -w "$CONTAINER_DIR"/"$PROJECT_DIR" \
  --env TERM=xterm-256color \
  eph-nvim/base:latest \
```

## Override Entrypoint

[Docs](https://docs.docker.com/engine/reference/run/#entrypoint-default-command-to-execute-at-runtime)

```console
docker run -it --entrypoint="" mysql bash
```
