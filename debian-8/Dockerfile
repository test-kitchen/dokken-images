FROM debian:8
LABEL maintainer="sean@sean.io"

RUN /usr/bin/apt-get update
RUN /usr/bin/apt-get -y install apt-transport-https curl iptables iputils-ping lsb-release lsof net-tools netcat nmap perl procps strace tcpdump telnet wget sudo

# Remove annoying tty service which consumes 100% CPU
RUN rm /etc/systemd/system/getty.target.wants/getty\@tty1.service

CMD [ "/bin/systemd" ]
