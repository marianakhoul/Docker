FROM ubuntu:18.04

MAINTAINER Maria Nakhoul <maria.nakhoul.9@gmail.com>

RUN apt-get update && apt-get install -y \
build-essential \
wget \

WORKDIR /usr/bin

RUN wget https://github.com/lh3/bwa/releases/download/v0.7.17/bwa-0.7.17.tar.bz2 && \
 tar jxf bwa-0.7.17.tar.bz2 && \
 rm bwa-0.7.17.tar.bz2 && \
 cd bwa-0.7.17 &&\
 make install
 
 ENV PATH=${PATH}:/usr/bin/bwa-0.7.17
