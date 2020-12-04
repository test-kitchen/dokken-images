FROM centos:6
LABEL maintainer="sean@sean.io"

RUN sed -i '/mirrorlist/d' /etc/yum.repos.d/*.repo
RUN sed -i -e 's/#baseurl/baseurl/g' /etc/yum.repos.d/*.repo
RUN sed -i -e 's/mirror.centos.org\/centos\/\$releasever/vault.centos.org\/6.10/g' /etc/yum.repos.d/*.repo
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
