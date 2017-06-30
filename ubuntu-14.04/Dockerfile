FROM ubuntu-upstart:14.04
LABEL maintainer="sean@sean.io"

RUN /usr/bin/apt-get update
RUN /usr/bin/apt-get -y install apt-transport-https curl emacs23-nox iptables iputils-ping lsof net-tools netcat nmap strace tcpdump telnet

CMD [ '/sbin/init' ]
