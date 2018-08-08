FROM amazonlinux:2
LABEL maintainer="sean@sean.io"

RUN yum -y install curl gnupg2 util-linux initscripts iptables iputils lsof nc net-tools nmap openssl procps strace systemd-sysv tcpdump telnet vim-minimal wget which ca-certificates sudo && \
    yum clean all && \
    rm -rf /var/cache/yum && \
    rm -rf /var/log/*

CMD [ "/usr/lib/systemd/systemd" ]
