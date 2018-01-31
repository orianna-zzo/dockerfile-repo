FROM alpine:latest
MAINTAINER Ziou Zheng <zhengziou@gmail.com>

# show user & current directory in the bash prompt
ENV PS1='\[\e[0;32m\][\u@\h \w \$]\[\e[m\]'

RUN apk update && apk add --no-cache bash bash-doc bash-completion \ 
    && sed -i -e 's/\/bin\/ash/\/bin\/bash/' /etc/passwd \ 
    && rm -f /bin/sh && ln -s /bin/bash /bin/sh 
