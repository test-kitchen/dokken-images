FROM fedora:24
LABEL maintainer="sean@sean.io"

RUN dnf --best --allowerasing -y install curl emacs-nox gnupg2 initscripts iptables iputils lsof nc net-tools nmap procps strace systemd-sysv tcpdump telnet vim-minimal wget which

CMD [ '/usr/lib/systemd/systemd' ]
