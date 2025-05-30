FROM ubuntu:24.04

ARG USER_NAME=snow

RUN yes | unminimize

RUN apt-get update && \
  apt-get install -y \
  man-db \
  sudo \
  locales \
  vim \
  curl \
  wget \
  dnsutils \
  iputils-ping \
  net-tools \
  telnet \
  traceroute \
  jq \
  git \
  golang

# Japanese
RUN locale-gen ja_JP.UTF-8
ENV LANG=ja_JP.UTF-8

# Add user without password
RUN useradd -m -s /bin/bash ${USER_NAME}
RUN passwd -d ${USER_NAME}
RUN gpasswd -a ${USER_NAME} sudo

USER ${USER_NAME}
WORKDIR /home/${USER_NAME}
