FROM ubuntu:14.04
LABEL maintainer="sean@sean.io"
ARG BUILD_DATE
ARG VCS_REF

LABEL org.label-schema.schema-version="1.0"
LABEL org.label-schema.build-date=$BUILD_DATE
LABEL org.label-schema.name="test-kitchen/dokken-images"
LABEL org.label-schema.description="A Docker container for testing ubuntu-14.04"
LABEL org.label-schema.vcs-url="https://github.com/test-kitchen/dokken-images"
LABEL org.label-schema.vcs-ref=$VCS_REF
LABEL org.label-schema.vendor="test-kitchen"

ENV DEBIAN_FRONTEND

# hadolint ignore=DL3041
RUN dnf -y install \
	/usr/bin/apt-get dist-upgrade -y && \
	/usr/bin/apt-get -y install \
	apt-transport-https \
	apt-utils \
	curl \
	cron \
	dirmngr \
	gnupg \
	iptables \
	iputils-ping \
	kmod \
	linux-base \
	locales \
	lsb-release \
	lsof \
	net-tools \
	netcat \
	nmap \
	perl \
	procps \
	strace \
	sudo \
	tcpdump \
	telnet \
	udev \
	vim-tiny \
	wget && \
	/usr/bin/apt-get clean && \
	/usr/bin/apt-get -y autoremove && \
	rm -rf /tmp/* /var/tmp/*

CMD [ "/sbin/init" ]
