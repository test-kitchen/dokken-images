FROM dokken/ubuntu-16.04
MAINTAINER Sean OMeara <sean@sean.io>

ARG CHANNEL=stable
ARG VERSION=2.3.4
ENV DEBIAN_FRONTEND=noninteractive PATH=/opt/chefdk/bin:/opt/chefdk/embedded/bin:/root/.chefdk/gem/ruby/2.4.0/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin

RUN wget --content-disposition \
"http://packages.chef.io/files/${CHANNEL}/chefdk/${VERSION}/ubuntu/16.04/chefdk_${VERSION}-1_amd64.deb" \
-O /tmp/chefdk.deb

RUN dpkg -i /tmp/chefdk.deb 

RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN curl -L https://get.docker.com | sh
