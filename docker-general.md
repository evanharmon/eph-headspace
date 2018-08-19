# DOCKER GENERAL

## Copy Localhost File to Docker Container
`$ docker cp filename 732e4ffd08fe:/home/dev/filename`

## Copy container file to localhost
`$ docker cp 732e4ffd08fe:/home/dev/filename filename`

## Set Hostname at run
`$ docker run -it -h nvim --name nvim evanharmon/hss-base-nvim:ubuntu zsh`

## Save Time Docker Files
run as one line to speed it up

## Search for container by name
`$ docker ps --filter "name=nvim"`

## View Container Logs
`$ docker logs <container name>`

## View log of Docker
`$ systemctl status docker`
