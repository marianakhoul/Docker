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

WORKDIR /usr/bin

RUN wget https://github.com/samtools/samtools/releases/download/1.9/samtools-1.9.tar.bz2 && \
	tar jxf samtools-1.9.tar.bz2 && \
	rm samtools-1.9.tar.bz2 && \
	cd samtools-1.9 && \
	make prefix=/usr/bin install

ENV PATH=${PATH}:/usr/bin/samtools-1.9 

