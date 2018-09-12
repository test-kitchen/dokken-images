FROM opensuse/leap:15
LABEL maintainer="sean@sean.io"

RUN zypper install -y aaa_base \
                      aaa_base-extras \
                      ca-certificates \
                      curl \
                      cron \
                      e2fsprogs \
                      file \
                      findutils \
                      glibc-locale \
                      grep \
                      hostname \
                      iproute2 \
                      iputils \
                      lsb-release \
                      ncurses-devel \
                      netcat \
                      net-tools \
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
