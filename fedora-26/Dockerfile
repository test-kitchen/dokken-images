FROM fedora:26
LABEL maintainer="sean@sean.io"

RUN dnf -y install passwd curl emacs-nox gnupg2 initscripts iptables iputils lsof nc net-tools nmap openssl procps strace systemd-sysv tcpdump telnet vim-minimal wget which ca-certificates sudo

CMD [ "/usr/lib/systemd/systemd" ]
