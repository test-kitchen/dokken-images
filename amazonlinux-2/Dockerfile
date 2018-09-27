FROM amazonlinux:2
LABEL maintainer="sean@sean.io"

RUN yum -y install \
    ca-certificates \
    cronie \
    curl \
    gnupg2 \
    initscripts \
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
    system-lsb-core \
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
