FROM fedora:33
LABEL maintainer="sean@sean.io"
ARG BUILD_DATE
ARG VCS_REF

LABEL org.label-schema.schema-version="1.0"
LABEL org.label-schema.build-date=$BUILD_DATE
LABEL org.label-schema.name="test-kitechen/dokken-images"
LABEL org.label-schema.description="A docker container for testing fedora-33"
LABEL org.label-schema.vcs-url="https://github.com/test-kitechen/dokken-images"
LABEL org.label-schema.vcs-ref=$VCS_REF
LABEL org.label-schema.vendor="test-kitchen"

RUN dnf -y install \
    binutils \
    ca-certificates \
    cronie \
    curl \
    dmidecode \
    ethtool \
    file \
    fipscheck \
    gnupg2 \
    hostname \
    initscripts \
    iproute \
    iptables \
    iputils \
    lsof \
    nc \
    net-tools \
    nmap \
    openssl \
    passwd \
    procps \
    strace \
    sudo \
    systemd-sysv \
    systemd-udev \
    tcpdump \
    telnet \
    util-linux \
    vim-minimal \
    wget \
    libxcrypt-compat \
    which && \
    dnf clean all && \
    rm -rf /var/log/* && \
    # Don't start any optional services.
    find /etc/systemd/system \
    /lib/systemd/system \
    -path '*.wants/*' \
    \( -name '*getty*' \
    -or -name '*systemd-logind*' \
    -or -name '*systemd-vconsole-setup*' \
    -or -name '*systemd-readahead*' \
    -or -name '*kdump*' \
    -or -name '*dnf-makecache*' \
    -or -name '*udev*' \) \
    -exec rm -v \{} \; && \
    systemctl set-default multi-user.target && \
    systemctl mask dev-hugepages.mount sys-fs-fuse-connections.mount network.service

CMD [ "/usr/lib/systemd/systemd" ]
