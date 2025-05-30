FROM ubuntu:24.04

ARG USER_NAME=snow

RUN yes | unminimize

RUN apt-get update && \
  apt-get install -y \
  man-db \
  sudo \
  vim \
  curl \
  wget \
  dnsutils \
  iputils-ping \
  net-tools \
  telnet \
  traceroute \
  software-properties-common \
  jq \
  git \
  golang

# # If latest Go is required
# RUN add-apt-repository ppa:longsleep/golang-backports && apt-get update && apt-get install -y golang-go
# ENV PATH=${PATH}:/home/${USER_NAME}/go/bin

# Japanese
RUN apt-get update && apt-get install -y locales && locale-gen ja_JP.UTF-8
ENV LANG=ja_JP.UTF-8

# Add user without password
RUN useradd -m -s /bin/bash ${USER_NAME}
RUN passwd -d ${USER_NAME}
RUN gpasswd -a ${USER_NAME} sudo

USER ${USER_NAME}
WORKDIR /home/${USER_NAME}
