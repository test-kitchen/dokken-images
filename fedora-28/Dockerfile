FROM fedora:28
LABEL maintainer="sean@sean.io"

RUN dnf -y install \
    ca-certificates \
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
    tcpdump \
    telnet \
    util-linux \
    vim-minimal \
    wget \
    which && \
    dnf clean all && \
    rm -rf /var/log/*

CMD [ "/usr/lib/systemd/systemd" ]
