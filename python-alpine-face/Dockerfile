FROM python:3.8-alpine3.13

MAINTAINER "qxw"

# https://www.cnblogs.com/yangzp/p/14609641.html
RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories \
    && apk update\
    && apk add --no-cache \
        bash \
    && mkdir /lib64 && ln -s /lib/libc.musl-x86_64.so.1 /lib64/ld-linux-x86-64.so.2

# ##################### face recognition,start #####################

RUN apk add cmake make gcc g++ \
    && pip install dlib==19.22.0 --verbose -i https://mirrors.aliyun.com/pypi/simple/

RUN pip install numpy==1.21.2 --verbose -i https://mirrors.aliyun.com/pypi/simple/

RUN apk add jpeg-dev openjpeg-dev zlib-dev \
    && pip install face_recognition -i https://mirrors.aliyun.com/pypi/simple/

RUN pip install tornado -i https://mirrors.aliyun.com/pypi/simple/

RUN apk add git
