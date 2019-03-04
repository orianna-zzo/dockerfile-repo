# dockerfile-repo

## Alpine-bash-docker
Alpine docker image using bash instead of ash.

### Get Image From Docker Hub

You can pull the image from the [Docker Hub](https://hub.docker.com/r/orianna/alpine-bash/)

```shell
$ docker pull orianna/alpine-bash
```

### Get Image From Dockerfile

You can build it from the Dockerfile.
Default base image: alpine:latest

```shell
$ docker build -t your-image-name:your-tag .
```

### Supported tags
* 0.1, 0.1-alpine3.7 (base image: alpine:3.7)
* 3.9, latest (base image: alpine:3.9)

