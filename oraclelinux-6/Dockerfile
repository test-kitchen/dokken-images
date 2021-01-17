FROM oraclelinux:6
LABEL maintainer="tsmith84@gmail.com"

RUN yum -y install \
    ca-certificates \
    cronie \
    curl \
    dmidecode \
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
    redhat-lsb-core \
    strace \
    sudo \
    tcpdump \
    telnet \
    upstart \
    util-linux \
    vim-minimal \
    wget \
    which && \
    yum clean all && \
    rm -rf /var/cache/yum && \
    rm -rf /var/log/*

CMD [ "/sbin/init" ]
