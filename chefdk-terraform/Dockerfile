FROM dokken/ubuntu-18.04:latest
MAINTAINER Sean OMeara <sean@sean.io>

ARG CHANNEL=stable
ARG CHEFDK_VERSION=3.2.30
ENV DEBIAN_FRONTEND=noninteractive PATH=/opt/chefdk/bin:/opt/chefdk/embedded/bin:/root/.chefdk/gem/ruby/2.5.0/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin

RUN wget -q --content-disposition \
"http://packages.chef.io/files/${CHANNEL}/chefdk/${CHEFDK_VERSION}/ubuntu/16.04/chefdk_${CHEFDK_VERSION}-1_amd64.deb" \
-O /tmp/chefdk.deb

RUN dpkg -i /tmp/chefdk.deb 

# Docker because kitchen-dokken needs it (for now)
RUN curl -L https://get.docker.com | sh

RUN apt-get install -y git

# Install terraform
RUN apt-get -y update
RUN apt-get -y install unzip
RUN wget -q https://releases.hashicorp.com/terraform/0.11.8/terraform_0.11.8_linux_amd64.zip
RUN unzip ./terraform_0.11.8_linux_amd64.zip
RUN mv terraform /usr/local/bin/

# do this last
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
