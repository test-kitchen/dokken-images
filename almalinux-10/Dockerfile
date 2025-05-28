FROM almalinux:10
LABEL maintainer="lance@osuosl.org"
ARG BUILD_DATE
ARG VCS_REF

LABEL org.opencontainers.image.created=$BUILD_DATE
LABEL org.opencontainers.image.title="test-kitchen/dokken-images"
LABEL org.opencontainers.image.description="A Docker container for testing almalinux-10"
LABEL org.opencontainers.image.source="https://github.com/test-kitchen/dokken-images"
LABEL org.opencontainers.image.revision=$VCS_REF
LABEL org.opencontainers.image.vendor="test-kitchen"
LABEL org.opencontainers.image.licenses="Apache-2.0"

RUN dnf -y install \
    at \
    binutils \
    bc \
    ca-certificates \
    cronie \
    crontabs \
    diffutils \
    dmidecode \
    e2fsprogs \
    ed \
    ethtool \
    file \
    gettext \
    glibc-langpack-en \
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
    make \
    man-db \
    openssl \
    patch \
    passwd \
    procps \
    procps-ng \
    psmisc \
    policycoreutils \
    strace \
    sudo \
    systemd-sysv \
    systemd-udev \
    tcpdump \
    telnet \
    util-linux \
    vim-minimal \
    time \
    wget \
    libxcrypt-compat \
    which && \
    dnf upgrade -y && \
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
    systemctl mask dev-hugepages.mount sys-fs-fuse-connections.mount network.service systemd-journal-flush.service

CMD [ "/usr/lib/systemd/systemd" ]
