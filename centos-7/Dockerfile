FROM centos:7
LABEL maintainer="sean@sean.io"

RUN yum -y install curl util-linux gnupg2 initscripts iptables iputils lsof nc net-tools nmap openssl procps strace systemd-sysv tcpdump telnet vim-minimal wget which ca-certificates sudo && \
    yum clean all && \
    rm -rf /var/cache/yum && \
    rm -rf /var/log/*

CMD [ "/usr/lib/systemd/systemd" ]
