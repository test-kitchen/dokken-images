FROM ubuntu-upstart:14.04
LABEL maintainer="sean@sean.io"

RUN /usr/bin/apt-get update
RUN /usr/bin/apt-get -y install apt-transport-https curl dirmngr gnupg iptables iputils-ping kmod lsb-release lsof net-tools netcat nmap perl procps strace tcpdump telnet vim wget sudo

CMD [ "/sbin/init" ]
