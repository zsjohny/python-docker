FROM ubuntu:16.04

# Update aliyun source
RUN sed -i -e 's/archive.ubuntu.com/mirrors.aliyun.com/g' /etc/apt/sources.list
# Apt Update
RUN apt-get update
RUN apt-get install -y software-properties-common
RUN add-apt-repository ppa:jonathonf/python-3.6
RUN apt-get update
RUN apt-get install -y python3.6 python3-pip
RUN ln -sf /usr/bin/python3.6 /usr/bin/python && ln -sf /usr/bin/pip3 /usr/bin/pip


