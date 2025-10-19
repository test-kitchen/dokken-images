FROM opensuse/leap:16.0
LABEL maintainer="tim@mondoo.com"
ARG BUILD_DATE
ARG VCS_REF

LABEL org.opencontainers.image.created=$BUILD_DATE
LABEL org.opencontainers.image.title="test-kitchen/dokken-images"
LABEL org.opencontainers.image.description="A Docker container for testing opensuse-leap-16.0"
LABEL org.opencontainers.image.source="https://github.com/test-kitchen/dokken-images"
LABEL org.opencontainers.image.revision=$VCS_REF
LABEL org.opencontainers.image.vendor="test-kitchen"
LABEL org.opencontainers.image.licenses="Apache-2.0"

# hadolint ignore=DL3037
RUN zypper update -y && \
  zypper install -y \
  aaa_base \
  aaa_base-extras \
  ca-certificates \
  cron \
  curl \
  dmidecode \
  e2fsprogs \
  file \
  findutils \
  glibc-locale \
  grep \
  gzip \
  hostname \
  iproute2 \
  iputils \
  less \
  lsb-release \
  ncurses-devel \
  net-tools \
  perl-Getopt-Long-Descriptive \
  sudo \
  systemd \
  sysvinit-tools \
  tar \
  time \
  timezone \
  traceroute \
  util-linux \
  vim \
  wget \
  which && \
  zypper clean && \
  rm -rf /var/log/* && \
  # Don't start any optional services.
  find /etc/systemd/system \
  /usr/lib/systemd/system \
  -path '*.wants/*' \
  \( -name '*getty*' \
  -or -name '*systemd-logind*' \
  -or -name '*systemd-vconsole-setup*' \
  -or -name '*systemd-readahead*' \
  -or -name '*udev*' \) \
  -exec rm -v {} \; && \
  systemctl set-default multi-user.target && \
  systemctl mask dev-hugepages.mount sys-fs-fuse-connections.mount network.service

CMD [ "/usr/lib/systemd/systemd" ]
