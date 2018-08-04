# dart-sass-docker
Docker image for [Sass/Scss](http://sass-lang.com/) compiler (development environment) using Dart Sass based on node:10.8.0-jessie.

## Get the Image
There are two ways to get the docker image. One is to pull it from docker hub, the other is to build it by yourself. 

### From Docker Hub
[Here](https://hub.docker.com/r/orianna/dart-sass/) is the image on the Docker Hub. The compressed size is 269MB (node image's size is 266MB). 
You can simply pull the latest image by:
```shell
$ docker pull orianna/dart-sass
```

Check the image, and this image is 680MB:
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
$ docker build -t orianna/dart-sass:1.10.3 -t orianna/dart-sass:latest .
```

Check the image, and this image is only 680MB now:
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

`-v your-sass-source-path:/sass` mounts your local sass source directory to the docker. `-v your-css-output-path:/output` defines where to save the static css file compiled by sass.

e.g.
```shell
$ docker run --name my-sass -v $(pwd):/sass -v $(pwd)/css:/output --rm -it orianna/dart-sass:latest SOURCE.scss DIST.css
```

To simplify it, you can config alias in `~/.profile` as follows:
```shell
alias sass="docker run -it --rm -v \$(pwd):/sass -v \$(pwd):/output orianna/dart-sass:latest"
```

With this alias, you can use the dart-sass image as if you use `sass` command locally:
```shell
$ sass SOURCE.scss DIST.css    
$ sass -v                      
$ sass -h                      
```

If you want to use shell in the container interactively, you can enter:
```shell
$ docker run --name my-sass -v $(pwd):/sass -v $(pwd)/css:/output --rm -it --entrypoint sh orianna/sass:latest
```

## Version
### v1.10.3:
- node:latest -> 10.8.0-jessie
- dart-sass 1.10.3 compiled with dart2js 2.0.0-dev.69.5 



 



