# DOCKER IMAGES

## Rename an Image
```console
docker tag myimage:latest mynewimage:latest
```

## Stop Docker Image <hash>
```console
docker stop <hash>
```

## Build Image
```console
docker build -t "neovim-docker" .
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
