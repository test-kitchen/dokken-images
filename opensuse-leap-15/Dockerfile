FROM opensuse/leap:15
LABEL maintainer="sean@sean.io"

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
                      lsb-release \
                      ncurses-devel \
                      net-tools \
                      netcat \
                      perl-Getopt-Long-Descriptive \
                      sudo \
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
    rm -rf /var/log/*

CMD [ "/bin/systemd" ]
