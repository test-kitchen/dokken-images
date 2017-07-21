FROM fedora:26
LABEL maintainer="sean@sean.io"

RUN dnf -y install curl emacs-nox gnupg2 initscripts iptables iputils lsof nc net-tools nmap procps strace systemd-sysv tcpdump telnet vim wget which

CMD [ '/usr/lib/systemd/systemd' ]
