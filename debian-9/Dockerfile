FROM debian:9
LABEL maintainer="sean@sean.io"

RUN /usr/bin/apt-get update
RUN /usr/bin/apt-get -y install apt-transport-https curl dirmngr emacs24-nox iptables iputils-ping lsb-release lsof net-tools netcat nmap perl procps strace systemd tcpdump telnet wget

CMD [ '/bin/systemd' ]
