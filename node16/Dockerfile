FROM debian:11.7

# Define
ARG USERNAME
ARG USER_UID=1000
ARG USER_GID=$USER_UID

# Install
RUN apt -y update && \
    apt -y upgrade && \
    apt -y install vim sudo tzdata curl git wget

# Setup Node
RUN curl -fsSL https://deb.nodesource.com/setup_16.x | bash - && \
    apt -y install nodejs && \
    npm install -g yarn

# Add User
RUN useradd --uid ${USER_UID} --create-home --shell /bin/bash -G sudo,root ${USERNAME} && \
    echo '%sudo ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers

# setting setup.sh
COPY setup.sh /var/setup.sh
RUN chmod 700 /var/setup.sh && \
    chown ${USERNAME}:${USERNAME} /var/setup.sh

CMD sh /var/setup.sh && bash
