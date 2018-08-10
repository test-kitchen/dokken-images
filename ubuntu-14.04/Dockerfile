FROM ubuntu-upstart:14.04
LABEL maintainer="sean@sean.io"

ENV DEBIAN_FRONTEND noninteractive
RUN /usr/bin/apt-get update && \
    /usr/bin/apt-get -y install \
    apt-transport-https \
    apt-utils \
    curl \
    cron \
    dirmngr \
    gnupg \
    iptables \
    iputils-ping \
    kmod \
    linux-base \
    locales \
    lsb-release \
    lsof \
    net-tools \
    netcat \
    nmap \
    perl \
    procps \
    strace \
    sudo \
    tcpdump \
    telnet \
    udev \
    vim-tiny \
    wget && \
    /usr/bin/apt-get clean && \
    /usr/bin/apt-get -y autoremove && \
    rm -rf /tmp/* /var/tmp/*

CMD [ "/sbin/init" ]
