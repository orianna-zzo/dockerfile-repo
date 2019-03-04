# dockerfile-repo

## pytorch-docker
Docker image for tensorflow

### Get the image
You can get the image from the [Docker Hub](https://hub.docker.com/r/orianna/pytorch/) or you can build it with the Dockerfile

#### From Docker Hub

You can pull the image from the [Docker Hub](https://hub.docker.com/r/orianna/pytorch/)

```shell
$ docker pull orianna/pytorch
```

##### Supported tags
* 1.0.1, latest (pytorch1.0.1, python 3.6, anaconda3-5.0.1, with tensorflow 1.13.0 for tensorboard and keras)

#### From Dockerfile

You can build it from the Dockerfile.
Base image: orianna/pytorch

```shell
$ docker build -t your-image-name:your-tag .
```

### How to Play it

Working directory is `/work`. You can mount working directory to your code directory on your host. You can go to your code directory and use the following command to start the container:

```shell
$ docker run -v $(pwd):/work  -p 8888:8888 -p 6006:6006 --rm -it orianna/pytorch
```

After you start your container, you can use the following command to start the Jupyter Notebook:

```shell
$ jupyter notebook --ip=0.0.0.0 --allow-root --NotebookApp.token=''
```

Now you can open your browser with 0.0.0.0:8888 and enjoy notebook!

You can also use tensorboard with the this command.
 
```shell
$ tensorboard --logdir $LOG_DIR --host 0.0.0.0
```

