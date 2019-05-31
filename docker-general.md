# DOCKER GENERAL

## Copy Localhost File to Docker Container

```console
$ docker cp filename 732e4ffd08fe:/home/dev/filename
```

## Copy container file to localhost

```console
$ docker cp 732e4ffd08fe:/home/dev/filename filename
```

## Set Hostname at run

```console
$ docker run -it -h nvim --name nvim evanharmon/hss-base-nvim:ubuntu zsh
```

## Save Time Docker Files

run as one line to speed it up

## Search for container by name

```console
$ docker ps --filter "name=nvim"
```

## View Container Logs

```console
$ docker logs <container name>
```

## View log of Docker

```console
$ systemctl status docker
```

## Mac docker.sock

located at `/private/var/run/docker.sock`
