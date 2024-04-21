FROM fedora:37
LABEL maintainer="tim@mondoo.com"
ARG BUILD_DATE
ARG VCS_REF

LABEL org.opencontainers.image.created=$BUILD_DATE
LABEL org.opencontainers.image.title="test-kitchen/dokken-images"
LABEL org.opencontainers.image.description="A Docker container for testing Fedora 37"
LABEL org.opencontainers.image.source="https://github.com/test-kitchen/dokken-images"
LABEL org.opencontainers.image.revision=$VCS_REF
LABEL org.opencontainers.image.vendor="test-kitchen"

# hadolint ignore=DL3041
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
  less \
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
  -exec rm -v {} \; && \
  systemctl set-default multi-user.target && \
  systemctl mask dev-hugepages.mount sys-fs-fuse-connections.mount network.service systemd-journal-flush.service

CMD [ "/usr/lib/systemd/systemd" ]
