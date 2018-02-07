FROM amazonlinux:latest
LABEL maintainer="sean@sean.io"

RUN yum -y install passwd upstart util-linux curl emacs-nox gnupg2 initscripts iptables iputils lsof nc net-tools nmap openssl procps strace tcpdump telnet vim wget which kmod &&\
    cat > /etc/sysconfig/network << "EOF"

CMD [ "/sbin/init" ]
