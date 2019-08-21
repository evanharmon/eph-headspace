# DOCKER COMPOSE

## Summary

Notes on using the `docker-compose` tool

## Standard YML File Name

docker-compose.yml

## Use Links Instead Of Ports

```YAML
links:
- mysql
- redis
```

## Example Compose file

```YAML
---
version: '3.2'

services:
  database:
    build: hss-couchbase-server
    ports:
      - "8091-8094:8091-8094"
      - "11207-11210:11207-11210"
      - "18091-18094:18091-18094"
  sync-gateway:
    build: hss-couchbase-mobile
    ports:
      - "4984-4985:4984-4985”
```

## Bash In To Compose Service

```console
$ docker-compose exec service_name bash
```

## Environment Variables

```
services:
  master:
    image: jenkins-master:latest
    environment:
      GITHUB_USER: ${GITHUB_USER}
      GITHUB_TOKEN: ${GITHUB_TOKEN}
```

## Tail And Follow Logs

```console
$ docker-compose logs --tail 50 -f hss-sync-gateway
```

## Persisent Volumes Example

```YAML
version: '3.2'
services:
  database:
    build: docker-database
    ...
    volumes:
     - db-data:/data
volumes:
  db-data
```

## Destroy Persistent Volumes

```console
$ docker-compose down -v
```

## Force Exit On Container Exit

`docker-compose up --abort-on-container-exit`
