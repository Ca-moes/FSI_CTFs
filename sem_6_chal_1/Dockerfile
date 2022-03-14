FROM ubuntu:20.04

# General
RUN useradd -ms /bin/bash seed && \
    echo "seed:seed" | chpasswd && \
    adduser seed sudo
RUN yes | unminimize && \  
    apt update && \
    apt full-upgrade
RUN apt install -y \ 
        sudo \
        man \
        nano \
        vim

# Lab specific
RUN apt install -y \         
        gcc \
        python3 \
        pip \
        netcat \
        checksec \
        gcc-multilib

RUN python3 -m pip install pwntools

USER seed
WORKDIR /home/seed

COPY . /home/seed

# docker build -t seed-labs .
# docker run --rm -it --privileged seed-labs
# seed$seed >> sudo apt install -y gdb