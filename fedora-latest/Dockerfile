FROM fedora:latest
LABEL maintainer="sean@sean.io"

RUN dnf -y install \
    binutils \
    ca-certificates \
    cronie \
    curl \
    dmidecode \
    ethtool \
    file \
    fipscheck \
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
