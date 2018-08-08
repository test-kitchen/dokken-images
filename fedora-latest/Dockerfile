FROM fedora:latest
LABEL maintainer="sean@sean.io"

RUN dnf -y install passwd curl util-linux gnupg2 initscripts iptables iputils lsof nc net-tools nmap openssl procps strace systemd-sysv tcpdump telnet vim-minimal wget which ca-certificates sudo && \
    dnf clean all && \
    rm -rf /var/log/*

CMD [ "/usr/lib/systemd/systemd" ]
