FROM debian:8
LABEL maintainer="sean@sean.io"

RUN /usr/bin/apt-get update
RUN /usr/bin/apt-get -y install apt-transport-https curl emacs24-nox iptables iputils-ping lsb-release lsof net-tools netcat nmap perl procps strace tcpdump telnet wget

CMD [ '/bin/systemd' ]
