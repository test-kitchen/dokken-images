FROM debian:7
LABEL maintainer="sean@sean.io"

RUN /usr/bin/apt-get update
RUN /usr/bin/apt-get -y install apt-transport-https curl emacs23-nox iptables iputils-ping lsb-release lsof net-tools netcat nmap strace tcpdump telnet wget

CMD [ '/sbin/init' ]
