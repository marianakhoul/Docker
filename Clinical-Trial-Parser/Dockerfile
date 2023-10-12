FROM ubuntu:20.04

RUN apt-get update 
RUN apt-get install -y --fix-missing \
    build-essential \
    wget \
    git \
    python3.8 \
    python3.8-dev \
    python3.8-distutils \
    python3-pip

#Install GO version 1.21.2
ARG GOLANG_VERSION=1.21.2
RUN wget https://go.dev/dl/go${GOLANG_VERSION}.linux-amd64.tar.gz && \
    rm -rf /usr/local/go && tar -C /usr/local -xzf go${GOLANG_VERSION}.linux-amd64.tar.gz && \
    rm go${GOLANG_VERSION}.linux-amd64.tar.gz

#Add GO to PATH
ENV PATH="${PATH}:/usr/local/go/bin"

#git clone repo
RUN git clone https://github.com/facebookresearch/Clinical-Trial-Parser.git

RUN pip3 install --upgrade pip
RUN pip3 install cmake
RUN pip3 install nltk
