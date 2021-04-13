# RABBIT MQ

## Summary

Notes on using running rabbit mq

## Resources

- [Tutorials](https://www.rabbitmq.com/tutorials/tutorial-one-go.html)
- [Docker](https://hub.docker.com/_/rabbitmq)

## Run Docker Image

exposes port to mac

```console
docker run -d --hostname my-rabbit -p 5672:5672 --name some-rabbit rabbitmq
```

verify server running

```console
docker logs some-rabbit
```

## Run Web Admin Tool

```console
docker run -d --hostname my-rabbit --name some-rabbit -p 5672:5672 -p 8080:15672 rabbitmq:3-management
```
