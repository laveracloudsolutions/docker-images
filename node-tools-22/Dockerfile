FROM ghcr.io/laveracloudsolutions/node:22-bullseye-slim

# install latest Google Chrome which will be used for running unit tests
RUN apt-get update  && \
    apt-get dist-upgrade -y && \
    apt-get install -qy \
    chromium \
    openjdk-17-jre \
    git \
    curl

RUN rm -rf /tmp/* /var/tmp/*

# "fake" dbus address to prevent errors
# https://github.com/SeleniumHQ/docker-selenium/issues/87
ENV DBUS_SESSION_BUS_ADDRESS=/dev/null

ENV CHROME_BIN=/usr/bin/chromium

# Install Angular ng CLI
RUN npm install -g @angular/cli

# Install commitizen
RUN npm install -g commitizen

# Set the default shell to bash instead of sh
ENV SHELL=/bin/bash

USER node
