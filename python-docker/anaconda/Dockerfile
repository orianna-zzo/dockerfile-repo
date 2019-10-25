FROM ubuntu:18.04
MAINTAINER Ziou Zheng <zhengziou@gmail.com>


# Install anaconda3 -> python3.6
# libgl1-mesa-glx libegl1-mesa libxrandr2 libxrandr2 libxss1 libxcursor1 libxcomposite1 libasound2 libxi6 libxtst6 for Anaconda GUI
RUN apt-get update \
    && apt-get install -yq --no-install-recommends ca-certificates wget bzip2 vim \   
    && apt-get install -yq --no-install-recommends libgl1-mesa-glx libegl1-mesa libxrandr2 libxrandr2 libxss1 libxcursor1 libxcomposite1 libasound2 libxi6 libxtst6 \
    && wget --quiet https://repo.continuum.io/archive/Anaconda3-2019.10-Linux-x86_64.sh \
    && sh Anaconda3-2019.10-Linux-x86_64.sh -b -p /root/anaconda3 \
    && rm Anaconda3-2019.10-Linux-x86_64.sh 

#     && echo '# added by Anaconda3 installer' > ~/.bashrc \
#     && echo 'export PATH="/root/anaconda3/bin:$PATH"' > ~/.bashrc \

# Set Environment
ENV PATH="/root/anaconda3/bin:$PATH"

RUN pip install --upgrade pip \
    && pip install tqdm

# Expose default port for jupyter notebook
EXPOSE 8888

# Decide working directory
WORKDIR /work

# Mount volume to host
VOLUME /work

