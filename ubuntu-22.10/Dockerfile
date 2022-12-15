FROM ubuntu:22.10
LABEL maintainer="tsmith84@gmail.com"
ARG BUILD_DATE
ARG VCS_REF

LABEL org.label-schema.schema-version="1.0"
LABEL org.label-schema.build-date=$BUILD_DATE
LABEL org.label-schema.name="test-kitchen/dokken-images"
LABEL org.label-schema.description="A Docker container for testing ubuntu-22.10"
LABEL org.label-schema.vcs-url="https://github.com/test-kitchen/dokken-images"
LABEL org.label-schema.vcs-ref=$VCS_REF
LABEL org.label-schema.vendor="test-kitchen"

ENV DEBIAN_FRONTEND=noninteractive

# hadolint ignore=DL3041
RUN dnf -y install \
	/usr/bin/apt-get dist-upgrade -y && \
	/usr/bin/apt-get -y install \
	apt-transport-https \
	apt-utils \
	curl \
	dbus \
	cron \
	dirmngr \
	dmidecode \
	gnupg \
	iproute2 \
	iptables \
	iputils-ping \
	kmod \
	less \
	linux-base \
	locales \
	lsb-release \
	lsof \
	net-tools \
	nmap \
	perl \
	procps \
	snapd \
	strace \
	sudo \
	systemd \
	tcpdump \
	telnet \
	tzdata \
	udev \
	vim-tiny \
	wget && \
	/usr/bin/apt-get clean && \
	/usr/bin/apt-get -y autoremove && \
	rm -rf /tmp/* /var/tmp/* && \
	# Don't start any optional services.
	find /etc/systemd/system \
	/lib/systemd/system \
	-path '*.wants/*' \
	\( -name '*getty*' \
	-or -name '*apt-daily*' \
	-or -name '*systemd-timesyncd*' \
	-or -name '*systemd-logind*' \
	-or -name '*systemd-vconsole-setup*' \
	-or -name '*systemd-readahead*' \
	-or -name '*udev*' \) \
	-exec rm -v {} \; && \
	systemctl set-default multi-user.target && \
	systemctl mask dev-hugepages.mount sys-fs-fuse-connections.mount network.service

CMD [ "/bin/systemd" ]
