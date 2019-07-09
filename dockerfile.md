# DOCKERFILE

## Summary

Notes on working with Dockefiles

## Resources

[Docs](https://docs.docker.com/engine/reference/builder/)
[Multistage Builds](https://docs.docker.com/develop/develop-images/multistage-build/)
[Best Practices](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/)

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

## Build Dockerfile From Std In With No Build Context

[Guide](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/#pipe-dockerfile-through-stdin)
can speed up builds by not using files in the directory

```console
cat Dockerfile | docker build my-image/base:latest -
```
