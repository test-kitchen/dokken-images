FROM ubuntu:17.04
LABEL maintainer="sean@sean.io"

RUN /usr/bin/apt-get update
RUN /usr/bin/apt-get -y install apt-transport-https curl dirmngr emacs24-nox gnupg iptables iputils-ping kmod lsb-release lsof net-tools netcat nmap perl procps strace systemd tcpdump telnet vim wget iproute2

CMD [ '/bin/systemd' ]
