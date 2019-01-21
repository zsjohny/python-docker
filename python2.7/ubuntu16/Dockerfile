FROM ubuntu:16.04

# Update aliyun source
RUN sed -i -e 's/archive.ubuntu.com/mirrors.aliyun.com/g' /etc/apt/sources.list

# Apt Update
RUN apt-get update
RUN apt-get install -y python-pip


