# DOCKER IMAGES

## Rename an Image

```console
docker tag myimage:latest mynewimage:latest
```

## Stop Docker Image <hash>

```console
docker stop <hash>
```

## List Docker Images

```console
docker images
```

## Download Image

```console
docker pull image-name
```

## Delete Docker Image <hash> from Downloaded Images

```console
docker rmi <hash>
```

## Get Image Info In JSON

```console
docker images repo1 --format "{{json . }}"
```

## Export Image Data And Parse With JQ

``console
docker images --format "{{json . }}" | jq .Repository | grep -v <exclude random stuff here> > images.txt
```
