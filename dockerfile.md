# DOCKERFILE

## Summary

Notes on working with Dockefiles

## Resources

[Docs](https://docs.docker.com/engine/reference/builder/)
[Multistage Builds](https://docs.docker.com/develop/develop-images/multistage-build/)

## Quiet Front-End no prompts

```
RUN DEBIAN_FRONTEND=noninteractive apt-get update
```

## Send Arguments to Dockerfile on Build

```console
docker build --build-arg userHome=$HOME .
```

## Use Argument in DockerFile

```
ARG userHome
ADD $userHome/.config /home/dev
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

## Extend \$PATH

```
ENV PATH="/root/go/bin:${PATH}"
```

## Expose Port

```
EXPOSE 8080/tcp
```

## Multistage Builds

Use multiple images in a Dockerfile and copy files between them

```
FROM eph-bin/base:latest AS bins
FROM eph-nvim/base:latest
COPY --from=bins /root/bins /root/bins
```

## Set ENV Variable From ARG

```docker
ARG A_VARIABLE
ENV an_env_var=$A_VARIABLE
```
