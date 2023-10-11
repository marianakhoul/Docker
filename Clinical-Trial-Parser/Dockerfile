from ubuntu:20.04

RUN apt-get update && apt-get install -y --fix-missing && \
    build-essential \
    wget \
    git 

#Install GO version 1.21.2
ARG GOLANG_VERSION=1.21.2
RUN wget https://go.dev/dl/go${GOLANG_VERSION}.linux-amd64.tar.gz && \
    rm -rf /usr/local/go && tar -C /usr/local -xzf go${GOLANG_VERSION}.linux-amd64.tar.gz && \
    rm go${GOLANG_VERSION}.linux-amd64.tar.gz

#Add GO to PATH
ENV PATH="${PATH}:/usr/local/go/bin"

#git clone repo
RUN git clone https://github.com/facebookresearch/Clinical-Trial-Parser.git

#git clone pytorch
RUN git clone --recursive https://github.com/pytorch/pytorch && \
    cd pytorch && \
    git submodule sync && \
    git submodule update --init --recursive

