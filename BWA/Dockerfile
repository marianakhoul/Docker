FROM ubuntu:xenial

MAINTAINER Maria Nakhoul <maria.nakhoul.9@gmail.com>

RUN apt-get update && apt-get install -y \
build-essential \
wget \
zlib1g-dev \
gcc \
bzip2 \
make && \
rm -rf /var/lib/apt/lists/*

WORKDIR /usr/bin

RUN wget https://github.com/lh3/bwa/releases/download/v0.7.17/bwa-0.7.17.tar.bz2 && \
		tar -xjf bwa-0.7.17.tar.bz2 &&\
		rm bwa-0.7.17.tar.bz2 && \
		cd bwa-0.7.17 &&\
		make
 
 ENV PATH=${PATH}:/usr/bin/bwa-0.7.17
