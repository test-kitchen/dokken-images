FROM centos:7
LABEL maintainer="sean@sean.io"

RUN yum -y install \
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
    system-lsb-core \
    systemd-sysv \
    tcpdump \
    telnet \
    util-linux \
    vim-minimal \
    wget \
    which && \
    yum clean all && \
    rm -rf /var/cache/yum && \
    rm -rf /var/log/*

CMD [ "/usr/lib/systemd/systemd" ]
