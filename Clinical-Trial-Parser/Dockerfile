FROM continuumio/anaconda3:latest

#Install GO version 1.21.2
ARG GOLANG_VERSION=1.21.2
RUN wget https://go.dev/dl/go${GOLANG_VERSION}.linux-amd64.tar.gz && \
    rm -rf /usr/local/go && tar -C /usr/local -xzf go${GOLANG_VERSION}.linux-amd64.tar.gz && \
    rm go${GOLANG_VERSION}.linux-amd64.tar.gz

#Add GO to PATH
ENV PATH="${PATH}:/usr/local/go/bin"

#Install/Update ONNX and Torch
RUN conda install -y onnx -c conda-forge
RUN conda install -y pytorch torchvision -c pytorch

#Not working
#RUN pip install pytext-nlp

#git clone repo
RUN git clone https://github.com/facebookresearch/Clinical-Trial-Parser.git




