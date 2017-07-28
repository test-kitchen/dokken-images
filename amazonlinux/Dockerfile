FROM amazonlinux:latest
LABEL maintainer="sean@sean.io"

RUN yum -y install upstart util-linux curl emacs-nox gnupg2 initscripts iptables iputils lsof nc net-tools nmap openssl procps strace tcpdump telnet vim wget which
RUN echo -e "NETWORKING=yes\nNETWORKING_IPV6=no\nHOSTNAME=dokken" > /etc/sysconfig/network

CMD [ '/sbin/init' ]
