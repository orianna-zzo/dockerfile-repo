# libsass-docker
Docker image for [Sass/Scss](http://sass-lang.com/) compiler (development environment) using Sassc and libsass based on alpine.

Warning: no `--watch` flag in libsass.

## Get the Image
There are two ways to get the docker image. One is to pull it from docker hub, the other is to build it by yourself. 

### From Docker Hub
The compressed size of the image on Docker Hub is only 4MB. 
You can simply pull the latest image by:
```shell
$ docker pull orianna/libsass-docker
```

Check the image, and this image is only 8.76MB now:
```shell
$ docker images
```

### Build the Image
If you have pulled the image from Docker Hub, you can skip this part.

Go to the repo's root and open the terminal:
```shell
$ docker build -t your/image-name:your-tag -t your/image-name:latest .
```
`-t` tags the image and one image can be tagged several times.

`your/image-name` is formatted by docker hub. It is not the official image so you have to put your docker cloud name before the slash.

`.` means from this directory.

e.g.
```shell
$ docker build -t orianna/libsass-docker-dev:3.5.2 -t orianna/sass-docker-dev:latest .
```

Check the image, and this image is only 94.0MB now:
```shell
$ docker images
```

Ref: The dockerfile refers to [this docker image jbergknoff/sass](https://hub.docker.com/r/jbergknoff/sass/)

## Run the Container
Run the docker container:
```shell
$ docker run --name container-name -v your-sass-source-path:/sass -v your-css-output-path:/output --rm -it your/image-name:your-tag SOURCE.scss DIST.css
```
`--name` defines the name of the container.

`-v` mounts the local directory to the docker.

`-p` defines the port mapping.

`--rm` means the container created by the command will be removed after the container is stopped.

`-i` means interactive.

`-t` means to open a terminal.

`-v your-sass-source-path:/sass` mounts your local sass source directory to the docker. `-v your-css-output-path:/output` defines where to save the static css compiled by sass.

e.g.
```shell
$ docker run --name my-libsass -v $(pwd):/sass -v $(pwd)/css:/output --rm -it orianna/libsass-docker:latest SOURCE.scss DIST.css
```

To simplify it, you can config alias in `~/.profile` as follows:
```shell
alias libsass-docker="docker run -it --rm -v \$(pwd):/sass -v \$(pwd):/output orianna/libsass-docker:latest"
```

With this alias, you can use the libsass-docker image as if you use `sass` command locally:
```shell
$ libsass-docker SOURCE.scss DIST.css    # sass SOURCE.scss DIST.css
$ libsass-docker -v                      # sass -v
$ libsass-docker -h                      # sass -h
```

If you want to use shell in the container interactively, you can enter:
```shell
$ docker run --name my-libsass -v $(pwd):/sass -v $(pwd)/css:/output --rm -it --entrypoint sh orianna/libsass-docker:latest
```

## Version
### v3.5.2:
sassc: 3.4.8-6-g43c4
libsass: 3.5.2-75-gedd2
sass2scss: 1.1.1
sass: 3.5



 



