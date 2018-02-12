FROM orianna/anaconda:latest
MAINTAINER Ziou Zheng <zhengziou@gmail.com>

# Install Tensorflow
RUN pip --no-cache-dir install --upgrade pip \ 
    && pip --no-cache-dir install --upgrade numpy \
    && pip --no-cache-dir install tensorflow

# Expose default port for tensorboard
EXPOSE 6006



