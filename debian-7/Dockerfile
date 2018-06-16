FROM debian:7
LABEL maintainer="sean@sean.io"

RUN /usr/bin/apt-get update
RUN /usr/bin/apt-get -y install apt-transport-https curl emacs23-nox iptables iputils-ping kmod lsb-release lsof net-tools netcat nmap procps strace tcpdump telnet wget locales sudo
RUN wget http://launchpadlibrarian.net/173841617/init-system-helpers_1.18_all.deb
RUN dpkg -i /init-system-helpers_1.18_all.deb
RUN rm -rf /sbin/initctl

CMD [ "/sbin/init" ]
