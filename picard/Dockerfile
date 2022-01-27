FROM ubuntu:18.04

MAINTAINER Maria Nakhoul <maria.nakhoul.9@gmail.com>

RUN apt-get update && apt-get install -y \
build-essential \
vim \
git \
zlib1g-dev && \
rm -rf /var/lib/apt/lists/* 

WORKDIR /usr/bin

RUN wget https://github.com/broadinstitute/picard/releases/download/2.26.10/picard.jar
    
ENV PATH=${PATH}:/usr/bin/picard.jar
