FROM ubuntu:16.04
MAINTAINER Ziou Zheng <zhengziou@gmail.com>


# install dependencies and python3
# build-essential -> h5py and others
# g++ gfortran -> numpy & pandas and others
# libfreetype6-dev libpng12-dev -> matplotlib
# cpio -> mkl
RUN apt-get update \
    && apt-get install -yq --no-install-recommends ca-certificates wget bzip2 vim \
    && wget --quiet https://repo.continuum.io/archive/Anaconda3-5.0.1-Linux-x86_64.sh \
    && sh Anaconda3-5.0.1-Linux-x86_64.sh -b -p /root/anaconda3 \
    && echo '# added by Anaconda3 installer' > ~/.bashrc \
    && echo 'export PATH="/root/anaconda3/bin:$PATH"' > ~/.bashrc \
    && rm Anaconda3-5.0.1-Linux-x86_64.sh


