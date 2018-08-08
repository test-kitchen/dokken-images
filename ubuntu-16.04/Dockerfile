FROM ubuntu:16.04
LABEL maintainer="sean@sean.io"

RUN /usr/bin/apt-get update
RUN /usr/bin/apt-get -y install apt-transport-https curl dirmngr gnupg iptables iputils-ping kmod lsb-release lsof net-tools netcat nmap perl procps python3 strace systemd tcpdump telnet vim wget sudo

# Remove annoying tty service which consumes 100% CPU
RUN rm /etc/systemd/system/getty.target.wants/getty\@tty1.service

CMD [ "/bin/systemd" ]
