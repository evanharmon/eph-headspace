# DOCKER COMPOSE

## Standard YML File Name
docker-compose.yml

## Use Links instead of ports
```
links:
- mysql
- redis
```

## Example Compose file
```
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

## Bash in to compose service
`$ docker-compose exec service_name bash`

## Environment variables
```
services:
  master:
    image: jenkins-master:latest
    environment:
      GITHUB_USER: ${GITHUB_USER}
      GITHUB_TOKEN: ${GITHUB_TOKEN}
```
