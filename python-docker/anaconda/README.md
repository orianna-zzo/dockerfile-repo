# dockerfile-repo

## anaconda-docker
Docker image with Anaconda and Jupyter Notebook

### Get the image
You can get the image from the [Docker Hub](https://hub.docker.com/r/orianna/anaconda/) or you can build it with the Dockerfile

#### From Docker Hub

You can pull the image from the [Docker Hub](https://hub.docker.com/r/orianna/anaconda/)

```shell
$ docker pull orianna/anaconda
```

##### Supported tags
* 3.6 (python 3.6, Anaconda3-5.2.0)
* 3.7, latest (python 3.7, Anaconda3-2019.10)

#### From Dockerfile

You can build it from the Dockerfile.
Base image: ubuntu:18.04

```shell
$ docker build -t your-image-name:your-tag .
```

### How to Play it

Working directory is `/work`. You can mount working directory to your code directory on your host. You can go to your code directory and use the following command to start the container:

```shell
$ docker run -v $(pwd):/work  -p 8888:8888 --rm -it orianna/anaconda
```

After you start your container, you can use the following command to start the Jupyter Notebook:

```shell
$ jupyter notebook --ip=0.0.0.0 --allow-root --NotebookApp.token=''
```

Now you can open your browser with 0.0.0.0:8888 and enjoy notebook!

