FROM amazonlinux:1
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

# currently causes failures in travis, but no where else
# RUN echo -e "NETWORKING=yes\nHOSTNAME=localhost.localdomain\nNOZEROCONF=yes" >/etc/sysconfig/network
CMD [ "/sbin/init" ]
