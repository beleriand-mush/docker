FROM ubuntu:16.04
MAINTAINER admin@beleriand.middleearth.net

ENV DEBIAN_FRONTEND noninteractive
ENV TERM linux
RUN echo 'debconf debconf/frontend select Noninteractive' | debconf-set-selections

RUN apt-get update -y
RUN apt-get install -y \
    build-essential cmake \
    sudo psmisc git curl vim telnet \
    libssl-dev \
    libpcre3 libpcre3-dev \
    libevent-2.0-5 libevent-dev libevent-openssl-2.0-5 \
    libboost-dev libboost-iostreams-dev libboost-program-options-dev
RUN useradd -ms /bin/bash bele && \
        mkdir -p /etc/sudoers.d && \
        echo "user ALL=(root) NOPASSWD:ALL" > /etc/sudoers.d/bele && \
        chmod 0440 /etc/sudoers.d/bele && \
        mkdir -p /mush && \
        chown -R bele /mush

USER bele
