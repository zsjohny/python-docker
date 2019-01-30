FROM python:3.4.9-alpine3.8
LABEL MAINTAINER Johny Zheng <shun.johny@gmail.com>

# https://github.com/docker-library/python/blob/dd36c08c1f94083476a8579b8bf20c4cd46c6400/3.6/alpine3.8/Dockerfile
# Update apk mirror
RUN cp /etc/apk/repositories /etc/apk/repositories.bak
RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories

# Install tools
RUN apk update && apk add curl bash
