FROM eurolinux/eurolinux-9
LABEL maintainer="tim@mondoo.com"
ARG BUILD_DATE
ARG VCS_REF

LABEL org.label-schema.schema-version="1.0"
LABEL org.label-schema.build-date=$BUILD_DATE
LABEL org.label-schema.name="test-kitchen/dokken-images"
LABEL org.label-schema.description="A Docker container for testing eurolinux-9"
LABEL org.label-schema.vcs-url="https://github.com/test-kitchen/dokken-images"
LABEL org.label-schema.vcs-ref=$VCS_REF
LABEL org.label-schema.vendor="test-kitchen"

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
