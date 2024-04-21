FROM amazonlinux:2
LABEL maintainer="sean@sean.io"
ARG BUILD_DATE
ARG VCS_REF

LABEL org.opencontainers.image.created=$BUILD_DATE
LABEL org.opencontainers.image.title="test-kitchen/dokken-images"
LABEL org.opencontainers.image.description="A Docker container for testing amazonlinux-2"
LABEL org.opencontainers.image.source="https://github.com/test-kitchen/dokken-images"
LABEL org.opencontainers.image.revision=$VCS_REF
LABEL org.opencontainers.image.vendor="test-kitchen"

# hadolint ignore=DL3033
RUN yum -y install \
	binutils \
	ca-certificates \
	cronie \
	curl \
	dmidecode \
	e2fsprogs \
	ethtool \
	file \
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
	system-lsb-core \
	systemd-sysv \
	tcpdump \
	telnet \
	util-linux \
	vim-minimal \
	wget \
	which && \
	yum upgrade -y && \
	yum clean all && \
	rm -rf /var/cache/yum && \
	rm -rf /var/log/* && \
	# Don't start any optional services.
	find /etc/systemd/system \
	/lib/systemd/system \
	-path '*.wants/*' \
	\( -name '*getty*' \
	-or -name '*postfix*' \
	-or -name '*systemd-logind*' \
	-or -name '*systemd-vconsole-setup*' \
	-or -name '*systemd-readahead*' \
	-or -name '*systemd-remount-fs*' \
	-or -name '*udev*' \) \
	-exec rm -v {} \; && \
	systemctl set-default multi-user.target && \
	systemctl mask dev-hugepages.mount sys-fs-fuse-connections.mount network.service

CMD [ "/usr/lib/systemd/systemd" ]
