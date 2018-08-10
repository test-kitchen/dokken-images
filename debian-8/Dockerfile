FROM debian:8
LABEL maintainer="sean@sean.io"

RUN /usr/bin/apt-get update && \
    /usr/bin/apt-get -y install \
    apt-transport-https \
    apt-utils \
    curl \
    dbus \
    dirmngr \
    gnupg \
    iptables \
    iputils-ping \
    kmod \
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
    systemd \
    tcpdump \
    telnet \
    udev \
    vim-tiny \
    wget && \
    /usr/bin/apt-get clean && \
    /usr/bin/apt-get -y autoremove && \
    rm -rf /tmp/* /var/tmp/* && \
    rm /etc/systemd/system/getty.target.wants/getty\@tty1.service # Remove annoying tty service which consumes 100% CPU

CMD [ "/bin/systemd" ]
