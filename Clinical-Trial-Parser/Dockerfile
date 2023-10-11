from ubuntu:20.04

RUN apt-get update 
RUN apt-get install -y --fix-missing \
    build-essential \
    wget \
    git \
    python3 \
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

RUN pip install pytext-nlp
RUN pip install nltk
RUN pip install numpy
