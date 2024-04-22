FROM oraclelinux:8
LABEL maintainer="tim@mondoo.com"
ARG BUILD_DATE
ARG VCS_REF

LABEL org.opencontainers.image.created=$BUILD_DATE
LABEL org.opencontainers.image.title="test-kitchen/dokken-images"
LABEL org.opencontainers.image.description="A Docker container for testing oraclelinux-8"
LABEL org.opencontainers.image.source="https://github.com/test-kitchen/dokken-images"
LABEL org.opencontainers.image.revision=$VCS_REF
LABEL org.opencontainers.image.vendor="test-kitchen"
LABEL org.opencontainers.image.licenses="Apache-2.0"

# hadolint ignore=DL3041
RUN dnf -y install \
	binutils \
	ca-certificates \
	cronie \
	curl \
	dmidecode \
	ethtool \
	file \
	gnupg2 \
	hostname \
	initscripts \
	iproute \
	iptables \
	iputils \
	lsof \
	nc \
	net-tools \
	nmap \
	openssl \
	passwd \
	procps \
	strace \
	sudo \
	systemd-sysv \
	systemd-udev \
	redhat-lsb-core \
	tcpdump \
	telnet \
	util-linux \
	vim-minimal \
	wget \
	which && \
	dnf upgrade -y && \
	dnf clean all && \
	rm -rf /var/log/* && \
	# Don't start any optional services.
	find /etc/systemd/system \
	/lib/systemd/system \
	-path '*.wants/*' \
	\( -name '*getty*' \
	-or -name '*dnf-makecache*' \
	-or -name '*sshd*' \
	-or -name '*systemd-logind*' \
	-or -name '*systemd-vconsole-setup*' \
	-or -name '*systemd-readahead*' \
	-or -name '*udev*' \) \
	-exec rm -v {} \; && \
	systemctl set-default multi-user.target && \
	systemctl mask dev-hugepages.mount sys-fs-fuse-connections.mount network.service systemd-journal-flush.service

CMD [ "/usr/lib/systemd/systemd" ]
