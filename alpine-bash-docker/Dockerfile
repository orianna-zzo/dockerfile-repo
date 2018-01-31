FROM alpine:latest
MAINTAINER Ziou Zheng <zhengziou@gmail.com>


COPY bashrc /etc/bashrc


RUN apk update && apk add --no-cache bash bash-doc bash-completion \ 
    && sed -i -e 's/\/bin\/ash/\/bin\/bash/' /etc/passwd \ 
    && rm -f /bin/sh && ln -s /bin/bash /bin/sh 
