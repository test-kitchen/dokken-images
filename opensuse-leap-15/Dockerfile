FROM opensuse/leap:15
LABEL maintainer="sean@sean.io"

RUN zypper install -y aaa_base \
                      util-linux \
                      perl-Getopt-Long-Descriptive \
                      which \
                      net-tools \
                      systemd-sysvinit \
                      curl \
                      tar \
                      glibc-locale \
                      ncurses-devel \
                      sudo \
                      wget && \
                      zypper clean && \
                      rm -rf /var/log/*

CMD [ "/bin/systemd" ]
