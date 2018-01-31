FROM python:3.6-alpine3.7
MAINTAINER Ziou Zheng <zhengziou@gmail.com>

# show user & current directory in the bash prompt
ENV PS1='\[\e[0;32m\][\u@\h \w \$]\[\e[m\]'

# using bash instead of ash
RUN apk update && apk add --no-cache bash bash-doc bash-completion \ 
    && sed -i -e 's/\/bin\/ash/\/bin\/bash/' /etc/passwd \ 
    && rm -f /bin/sh && ln -s /bin/bash /bin/sh 


# install python 3 packages
COPY requirements.txt /requirements.txt
RUN apk add --no-cache g++ gfortran
RUN pip install --upgrade pip && pip install -r requirements.txt

CMD ["/bin/bash"]
