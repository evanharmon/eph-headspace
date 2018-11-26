# DOCKER CONTAINERS

## List Docker Container Processes
```console
$ docker ps -a
```

## Create Docker Container
```console
$ docker create --name my-container-name image_name
```

## Run an Image
```console
$ docker run --name my-container-name -d image_name
```

## Start an Image and Leave Running
```console
$ docker run -t -d -p 4984-4985:4984-4985 "couchbase-mobile"
```

## Run Container with Full Color Support
```console
$ docker run -it -e "TERM=xterm-256color" image_name bash -l
```

## Enter Docker Container as Root
```console
$ docker exec -u 0 -it mycontainer bash
```

## Remove Stopped Docker Container <hash> (NOT DELETE)
```console
$ docker rm <hash>
```

## Remove All Running Containers
```console
$ docker rm -f $(docker ps -aq)
```

## Bash Access
```console
$ docker exec -it my-container-name bash
```

## Docker Bind Container to Host Port / Expose Port
```console
$ docker run -d -p 80:3000
```

## Leave Container But Keep It Running
`<ctrl>pq`

## Check Stats On Docker Container
```console
$ docker stats <UUID>
```

## Check Log
```console
$ docker logs <UUID>
```

## Check Events
```console
$ docker events --since 1h
```

## Run Docker Container Without Default Seccomp Profile
Avoids the `could not launch process: fork/exec ...: operation not permitted`
error
[Docs](https://docs.docker.com/engine/security/seccomp/#significant-syscalls-blocked-by-the-default-profile)
```console
$ docker run --rm -it --security-opt seccomp=unconfined debian:jessie \
    unshare --map-root-user --user sh -c whoami
```
