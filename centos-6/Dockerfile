FROM centos:6
LABEL maintainer="sean@sean.io"

RUN yum -y install curl util-linux gnupg2 initscripts iptables iputils lsof nc net-tools nmap openssl procps strace tcpdump telnet vim-minimal wget which ca-certificates sudo && \
    yum clean all && \
    rm -rf /var/cache/yum && \
    rm -rf /var/log/*

CMD [ "/sbin/init" ]
