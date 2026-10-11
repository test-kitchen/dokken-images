FROM registry.suse.com/bci/bci-init:15.7
LABEL maintainer="lance@osuosl.org"
ARG BUILD_DATE
ARG VCS_REF

LABEL org.opencontainers.image.created=$BUILD_DATE
LABEL org.opencontainers.image.title="test-kitchen/dokken-images"
LABEL org.opencontainers.image.description="A Docker container for testing sles-15"
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
  gawk \
  glibc-locale \
  grep \
  gzip \
  hostname \
  insserv-compat \
  iproute2 \
  iputils \
  less \
  lsb-release \
  ncurses-devel \
  net-tools \
  netcat-openbsd \
  procps \
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
  zypper clean -a && \
  rm -rf /var/log/* /tmp/* /var/tmp/* && \
  # Keep pid_one_command: /bin/systemd working like the openSUSE images.
  { test -e /bin/systemd || ln -s /usr/lib/systemd/systemd /bin/systemd; } && \
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
  systemctl mask dev-hugepages.mount sys-fs-fuse-connections.mount network.service && \
  # Let systemd generate a unique machine-id in each container
  truncate -s 0 /etc/machine-id

# The bci-init healthcheck is meaningless when kitchen-dokken overrides pid 1.
HEALTHCHECK NONE

CMD [ "/usr/lib/systemd/systemd" ]
