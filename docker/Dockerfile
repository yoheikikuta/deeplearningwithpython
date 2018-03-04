FROM nvidia/cuda:8.0-cudnn6-devel-ubuntu16.04


RUN apt-get update && apt-get install -y \
  git \
  python3.5 \
  python3-pip \
  python3-dev


RUN pip3 install --upgrade pip

RUN echo "alias python=python3" >> $HOME/.bashrc && \
    echo "alias pip=pip3" >> $HOME/.bashrc

COPY ./requirements.txt /requirements.txt
RUN pip install -r /requirements.txt


RUN useradd docker -u 1000 -s /bin/bash -m
USER docker

WORKDIR /work

ENTRYPOINT ["/bin/bash"]
