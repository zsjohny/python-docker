FROM alpine

# Update apk mirror
RUN cp /etc/apk/repositories /etc/apk/repositories.bak
RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories

# Install tools
RUN apk update && apk add curl

RUN apk add python py-pip
