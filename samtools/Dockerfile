FROM ubuntu:18.04

MAINTAINER Maria Nakhoul <maria.nakhoul.9@gmail.com>

RUN apt-get -y update && apt-get -y install && \
wget \
libncurses5-dev \
zlib1g-dev \
libbz2-dev \
liblzma-dev \
libcurl3-dev && \
apt-get clean && \
rm -rf /var/lib/apt/lists/*

