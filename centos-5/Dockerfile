FROM centos:5
LABEL maintainer="sean@sean.io"

RUN sed -i '/mirrorlist/d' /etc/yum.repos.d/*.repo
RUN sed -i -e 's/#baseurl/baseurl/g' /etc/yum.repos.d/*.repo
RUN sed -i -e 's/mirror.centos.org\/centos\/\$releasever/vault.centos.org\/5.11/g' /etc/yum.repos.d/*.repo
RUN yum -y install curl emacs-nox gnupg2 initscripts iptables iputils lsof nc net-tools nmap openssl procps strace tcpdump telnet vim-minimal wget which

CMD [ "/sbin/init" ]
