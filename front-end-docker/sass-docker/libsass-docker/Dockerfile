FROM alpine:latest
MAINTAINER Zi'ou Zheng <zhengziou@gmail.com>

# Install Sass & Clean 
#    -- copyright from https://github.com/jbergknoff/Dockerfile/tree/master/sass
RUN apk --no-cache --update add git build-base libstdc++ \ 
    && git clone https://github.com/sass/sassc.git && cd sassc \ 
    && git clone https://github.com/sass/libsass.git \
    && SASS_LIBSASS_PATH=/sassc/libsass make \
    && mv bin/sassc /usr/bin/sass \ 
    && cd / && rm -rf /sassc && apk del git build-base && rm -rf /var/cache/apk/*

# Decide working directory
WORKDIR /sass

# Mount volume to host
VOLUME /sass
VOLUME /output

ENTRYPOINT [ "sass" ]
