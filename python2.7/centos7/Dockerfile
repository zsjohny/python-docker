FROM centos:7

# aliyun mirrors
RUN yum install -y wget && wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo
RUN yum makecache

RUN yum install -y epel-release
RUN yum install -y python-pip
