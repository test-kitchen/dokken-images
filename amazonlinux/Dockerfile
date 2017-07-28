FROM amazonlinux:latest
LABEL maintainer="sean@sean.io"

RUN yum -y install upstart util-linux curl emacs-nox gnupg2 initscripts iptables iputils lsof nc net-tools nmap openssl procps strace tcpdump telnet vim wget which

cat >/etc/sysconfig/network <<EOL
NETWORKING=yes
NETWORKING_IPV6=no
HOSTNAME=dokken
EOL

CMD [ '/sbin/init' ]
