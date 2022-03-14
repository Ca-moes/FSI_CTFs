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
        gdb \
        make \
        zsh \
        gcc-multilib \
        netcat \
        checksec

RUN python3 -m pip install pwntools

USER seed
WORKDIR /home/seed

COPY . /home/seed