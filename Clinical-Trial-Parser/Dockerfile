FROM ubuntu:18.04


RUN apt-get update && apt-get upgrade -y && apt-get clean && apt-get install -y \
build-essential \
wget \
curl \
git \
python3.7 \
python3.7-dev \
python3.7-distutils \


ARG GOLANG_VERSION=1.20.4
RUN wget https://go.dev/dl/go${GOLANG_VERSION}.linux-amd64.tar.gz && \
    rm -rf /usr/local/go && tar -C /usr/local -xzf go${GOLANG_VERSION}.linux-amd64.tar.gz && \
    rm go${GOLANG_VERSION}.linux-amd64.tar.gz
ENV PATH="${PATH}:/usr/local/go/bin"

