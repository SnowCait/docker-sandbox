FROM ubuntu:22.04

ARG USER_NAME=user
ARG GROUP_NAME=user

# Install Homebrew
RUN apt-get update && apt-get install -y build-essential procps curl file git
RUN NONINTERACTIVE=1 /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Add user
RUN groupadd -r ${GROUP_NAME} && useradd -r -g ${GROUP_NAME} ${USER_NAME}
RUN chown -R ${USER_NAME}:${GROUP_NAME} /home/linuxbrew
USER ${USER_NAME}
WORKDIR /home/${USER_NAME}

# Add path
RUN /home/linuxbrew/.linuxbrew/bin/brew shellenv >> /home/${USER_NAME}/.bashrc
