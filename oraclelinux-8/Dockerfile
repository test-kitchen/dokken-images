FROM oraclelinux:8
LABEL maintainer="tsmith84@gmail.com"

RUN dnf -y install \
    ca-certificates \
    cronie \
    curl \
    dmidecode \
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
