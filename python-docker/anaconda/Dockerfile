FROM ubuntu:16.04
MAINTAINER Ziou Zheng <zhengziou@gmail.com>


# Install anaconda3 -> python3.6
RUN apt-get update \
    && apt-get install -yq --no-install-recommends ca-certificates wget bzip2 vim \
    && wget --quiet https://repo.continuum.io/archive/Anaconda3-5.0.1-Linux-x86_64.sh \
    && sh Anaconda3-5.0.1-Linux-x86_64.sh -b -p /root/anaconda3 \
    && echo '# added by Anaconda3 installer' > ~/.bashrc \
    && echo 'export PATH="/root/anaconda3/bin:$PATH"' > ~/.bashrc \
    && rm Anaconda3-5.0.1-Linux-x86_64.sh

# Set Environment
ENV PATH="/root/anaconda3/bin:$PATH"

# Expose default port for jupyter notebook
EXPOSE 8888

# Decide working directory
WORKDIR /work

# Mount volume to host
VOLUME /work

