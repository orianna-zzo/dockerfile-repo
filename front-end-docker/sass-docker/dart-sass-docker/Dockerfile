FROM node:latest
MAINTAINER Zi'ou Zheng <zhengziou@gmail.com>

# Install Sass 
RUN npm install -g sass

# Decide working directory
WORKDIR /sass

# Mount volume to host
VOLUME /sass
VOLUME /output

ENTRYPOINT [ "sass" ]

