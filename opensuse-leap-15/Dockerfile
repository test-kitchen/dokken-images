FROM opensuse/leap:15.2
LABEL maintainer="sean@sean.io"
ARG BUILD_DATE
ARG VCS_REF

LABEL org.label-schema.schema-version="1.0"
LABEL org.label-schema.build-date=$BUILD_DATE
LABEL org.label-schema.name="test-kitchen/dokken-images"
LABEL org.label-schema.description="A Docker container for testing opensuse-leap-15"
LABEL org.label-schema.vcs-url="https://github.com/test-kitchen/dokken-images"
LABEL org.label-schema.vcs-ref=$VCS_REF
LABEL org.label-schema.vendor="test-kitchen"

RUN zypper update -y && \
    zypper install -y aaa_base \
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
                      insserv-compat \
                      iproute2 \
                      iputils \
                      less \
                      lsb-release \
                      ncurses-devel \
                      net-tools \
                      netcat \
                      perl-Getopt-Long-Descriptive \
                      sudo \
                      systemd \
                      systemd-sysvinit \
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
    -exec rm -v \{} \; && \
    systemctl set-default multi-user.target && \
    systemctl mask dev-hugepages.mount sys-fs-fuse-connections.mount network.service

CMD [ "/bin/systemd" ]
