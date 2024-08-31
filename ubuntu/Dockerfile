FROM ubuntu:22.04

ARG USER_NAME=snow

RUN yes | unminimize

RUN apt install -y \
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
  jq
RUN add-apt-repository ppa:longsleep/golang-backports && apt install -y golang-go

# Add user without password
RUN useradd -m -s /bin/bash ${USER_NAME}
RUN passwd -d ${USER_NAME}
RUN gpasswd -a ${USER_NAME} sudo

USER ${USER_NAME}
WORKDIR /home/${USER_NAME}
