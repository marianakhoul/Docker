FROM ubuntu:18.04

MAINTAINER Maria Nakhoul <maria.nakhoul.9@gmail.com>

RUN apt-get update && apt-get install -y \
build-essential \
vim \
git \
zlib1g-dev && \
rm -rf /var/lib/apt/lists/* 

WORKDIR /usr/bin

RUN git clone https://github.com/lh3/bwa.git && \
	cd bwa && \
	make && \

 ENV PATH=${PATH}:/usr/bin/bwa
