FROM ubuntu:16.04
LABEL maintainer="sean@sean.io"

RUN /usr/bin/apt-get update
RUN /usr/bin/apt-get -y install apt-transport-https curl emacs23-nox iptables iputils-ping kmod lsof net-tools netcat nmap strace tcpdump telnet

CMD [ '/bin/systemd' ]
