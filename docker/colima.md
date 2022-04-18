# COLIMA

using colima with docker

## Resources

- [Colima Github Repo](https://github.com/abiosoft/colima)

## Daemon connection errors

Cannot connect to the Docker daemon at unix:///var/run/docker.sock

do not use `--container-daemon-socket` flag. The problem is

set `DOCKER_HOST` env variable
set `DOCKER_CONTEXT` env variable

```console
export DOCKER_HOST=$(docker context inspect --format '{{.Endpoints.docker.Host}}')
export DOCKER_CONTEXT='colima'
```

## docker-credential-desktop errors

docker-credential-desktop executable file not found in $PATH

adjust `~/.docker/config.json` and delete `credsStore` property

```
{
	"auths": {},
	"credsStore": "desktop",
	"currentContext": "colima"
}
```
