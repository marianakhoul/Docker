FROM ubuntu:18.04

MAINTAINER Maria Nakhoul <maria.nakhoul.9@gmail.com>

RUN apt-get update && apt-get install -y \
build-essential \
wget \
libncurses5-dev \
zlib1g-dev \
libbz2-dev \
liblzma-dev \
make && \
rm -rf /var/lib/apt/lists/*

RUN wget 'https://github.com/lh3/bwa/releases/download/v0.7.15/bwakit-0.7.15_x64-linux.tar.bz2' -O bwakit-0.7.15.tar.bz2 && \
tar xf bwakit-0.7.15.tar.bz2 && \
rm bwakit-0.7.15.tar.bz2 && \
mv bwa.kit/bwa bwa && \
rm -rf bwa.kit

