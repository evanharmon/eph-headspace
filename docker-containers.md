# DOCKER CONTAINERS

## List Docker Container Processes
`$ docker ps -a`

## Create Docker Container
`$ docker create --name my-container-name image_name`

## Run an Image
`$ docker run --name my-container-name -d image_name`

## Start an Image and Leave Running
`$ docker run -t -d -p 4984-4985:4984-4985 "couchbase-mobile"`

## Run Container with Full Color Support
`$ docker run -it -e "TERM=xterm-256color" image_name bash -l`

## Enter Docker Container as Root
`$ docker exec -u 0 -it mycontainer bash`

## Remove Stopped Docker Container <hash> (NOT DELETE)
`$ docker rm <hash>`

## Remove All Running Containers
`$ docker rm -f $(docker ps -aq)`

## Bash Access
`$ docker exec -it my-container-name bash`

## Docker Bind Container to Host Port
`$ docker run -d -p 80:3000`

## Leave Container But Keep It Running
`<ctrl>pq`

## Check Stats On Docker Container
`$ docker stats <UUID>`

## Check Log
`$ docker logs <UUID>`

## Check Events
`$ docker events --since 1h`
