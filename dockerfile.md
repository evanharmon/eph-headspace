# DOCKERFILE

## Quiet Front-End no prompts
`RUN DEBIAN_FRONTEND=noninteractive apt-get update`

## Send Arguments to Dockerfile on Build
```console
$ docker build --build-arg userHome=$HOME .
```

## Use Argument in DockerFile
```
ARG userHome
add $userHome/.config /home/dev
```

## Change Directory
`WORKDIR /home/dev/.bin`

## Change User In Dockerfile
`USER dev2`

## Set Environment Variable In Dockerfile
`ENV HOSTNAME nvim`

## Run a script In A Dockerfile
`CMD ["/bin/zsh"]`

## Copy a file/directory
Trailing slash is considered a directory
`COPY hss-cfg/ .hss-cfg/`

## Keep running
in a shell file do:
```
While true
do
    tail -f /dev/null & wait ${!}
done
```

## Extend $PATH
```console
ENV PATH="/root/go/bin:${PATH}"
```
