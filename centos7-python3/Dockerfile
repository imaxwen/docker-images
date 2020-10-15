FROM centos:7

LABEL MAINTAINER="Max Wen<maxwen.me@gmail.com>"

ENV PYTHON_VERSION=3.7.9

RUN rpm --import /etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7 && \
    yum -y update && \
    yum install -y wget make gcc zlib-devel libffi-devel bzip2-devel openssl-devel ncurses-devel sqlite-devel readline-devel tk-devel gdbm-devel libuuid-devel xz-devel && \
    cd /usr/src && \
    wget https://www.python.org/ftp/python/${PYTHON_VERSION}/Python-${PYTHON_VERSION}.tgz && \
    tar xzf Python-${PYTHON_VERSION}.tgz && \
    cd /usr/src/Python-${PYTHON_VERSION} && \
    ./configure --enable-optimizations && \
    make altinstall && \
    rm /usr/src/Python-${PYTHON_VERSION}.tgz && \
    yum clean all

CMD ["/bin/bash"]
