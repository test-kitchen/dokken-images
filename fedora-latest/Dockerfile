FROM fedora:latest
LABEL maintainer="sean@sean.io"

RUN dnf -y install initscripts systemd-sysv net-tools procps-ng which yum

CMD [ '/usr/lib/systemd/systemd' ]
