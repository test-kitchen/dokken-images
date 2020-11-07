FROM centos:8
LABEL maintainer="tsmith84@gmail.com"

RUN dnf -y install \
    binutils \
    ca-certificates \
    cronie \
    curl \
    dmidecode \
    ethtool \
    file \
    gnupg2 \
    hostname \
    initscripts \
    iproute \
    iptables \
    iputils \
    lsof \
    nc \
    net-tools \
    nmap \
    openssl \
    passwd \
    procps \
    strace \
    sudo \
    systemd-sysv \
    systemd-udev \
    redhat-lsb-core \
    tcpdump \
    telnet \
    util-linux \
    vim-minimal \
    wget \
    which && \
    dnf upgrade -y && \
    dnf clean all && \
    rm -rf /var/log/*

CMD [ "/usr/lib/systemd/systemd" ]
