FROM maven:3.6.0-jdk-8

ARG uid
ARG gid

RUN apt-get update \
    && apt-get install -y bash git \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/*

RUN groupadd -g ${gid} developer \
    && useradd -g developer -u ${uid} -m developer

USER developer

RUN mkdir -p ~/.ssh \
    && mkdir -p ~/.vscode-server-insiders \
    && mkdir -p ~/aim/m3repo \
    && echo 'eval `ssh-agent -s`' >> ~/.profile

ENV HOME=/home/developer
ENV SHELL=/bin/bash
