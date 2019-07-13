FROM fedora:latest
LABEL maintainer="sean@sean.io"

RUN dnf -y install \
    ca-certificates \
    cronie \
    curl \
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
    tcpdump \
    telnet \
    util-linux \
    vim-minimal \
    wget \
    libxcrypt-compat \
    which && \
    dnf clean all && \
    rm -rf /var/log/*

CMD [ "/usr/lib/systemd/systemd" ]
