FROM ubuntu:18.04
LABEL maintainer="sean@sean.io"

RUN /usr/bin/apt-get update; /usr/bin/apt-get -y install apt-transport-https curl dirmngr gnupg iptables iputils-ping kmod lsb-release lsof net-tools netcat nmap perl procps strace systemd tcpdump telnet vim wget iproute2

CMD [ "/bin/systemd" ]
