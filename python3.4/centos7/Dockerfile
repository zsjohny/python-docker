FROM centos:7.4.1708
LABEL MAINTAINER Johny Zheng <shun.johny@gmail.com>

WORKDIR /tmp
ENV PYTHON_VERSION=3.4.9

RUN yum install -y epel-release
RUN yum -y install wget sqlite-devel xz gcc automake make zlib-devel openssl-devel tar
RUN yum clean all

# Install Python
RUN wget https://www.python.org/ftp/python/${PYTHON_VERSION}/Python-${PYTHON_VERSION}.tar.xz && \
tar xvf Python-${PYTHON_VERSION}.tar.xz  && cd Python-${PYTHON_VERSION} && ./configure && make && make install &&  \
rm -rf /tmp/{Python-${PYTHON_VERSION}.tar.xz,${PYTHON_VERSION}}
RUN ln -sf /usr/bin/python2.7 /usr/bin/python2
RUN ln -sf /usr/local/bin/python3 /usr/bin/python && ln -sf /usr/local/bin/pip3 /usr/bin/pip
RUN sed -i 's@/usr/bin/python@/usr/bin/python2@g' /usr/bin/yum
RUN sed -i 's@/usr/bin/python@/usr/bin/python2@g' /usr/libexec/urlgrabber-ext-down

# if this is called "PIP_VERSION", pip explodes with "ValueError: invalid truth value '<VERSION>'"
ENV PYTHON_PIP_VERSION 19.0.1

RUN set -ex; \
	\
	wget -O get-pip.py 'https://bootstrap.pypa.io/get-pip.py'; \
	\
	python get-pip.py \
		--disable-pip-version-check \
		--no-cache-dir \
		"pip==$PYTHON_PIP_VERSION" \
	; \
	pip --version; \
	\
	find /usr/local -depth \
		\( \
			\( -type d -a \( -name test -o -name tests \) \) \
			-o \
			\( -type f -a \( -name '*.pyc' -o -name '*.pyo' \) \) \
		\) -exec rm -rf '{}' +; \
	rm -f get-pip.py

CMD ["python3"]
