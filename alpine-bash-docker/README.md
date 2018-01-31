# dockerfile-repo

## Alpine-bash-docker
Alpine docker image using bash instead of ash.

## Get the image
You can get the image from Docker Hub or you can build it with Dockerfile

### From Docker Hub

```shell
$ docker pull orianna/alpine-bash
```

### From Dockerfile

You can build from the Dockerfile.

```shell
$ docker build -t your-image-name:your-tag .
```

## Issue:

The bash prompt cannot show the current directory. If you want to show the directory in the interactive tty, please `source /etc/bashrc` first.

