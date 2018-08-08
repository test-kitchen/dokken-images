FROM ubuntu:18.04
LABEL maintainer="sean@sean.io"

RUN /usr/bin/apt-get update && \
    /usr/bin/apt-get -y install \
    apt-transport-https \
    curl \
    dirmngr \
    gnupg \
    iproute2 \
    iptables \
    iputils-ping \
    kmod \
    lsb-release \
    lsof \
    net-tools \
    netcat \
    nmap \
    perl \
    procps \
    strace \
    sudo \
    systemd \
    tcpdump \
    telnet \
    vim-tiny \
    wget && \
    rm /etc/systemd/system/getty.target.wants/getty\@tty1.service # Remove annoying tty service which consumes 100% CPU

CMD [ "/bin/systemd" ]
