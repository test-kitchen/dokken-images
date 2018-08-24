FROM opensuse/leap:42
LABEL maintainer="sean@sean.io"

RUN zypper install -y aaa_base \
                      util-linux \
                      perl-Getopt-Long-Descriptive \
                      which \
                      net-tools \
                      systemd-sysvinit \
                      aaa_base-extras \
                      ca-certificates \
                      curl \
                      tar \
                      cron \
                      e2fsprogs \
                      file \
                      findutils \
                      glibc-locale \
                      ncurses-devel \
                      sudo \
                      wget && \
                      zypper clean && \
                      rm -rf /var/log/*

CMD [ "/bin/systemd" ]
