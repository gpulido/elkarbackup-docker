# Generate Elkarbackup DEB package using a container

# docker run -d \
#	-v $(pwd):/export \
# -e "GIT_REPO=https://github.com/elkarbackup/elkarbackup"
#	-e "PHP_VERSION=7" \
#	--name eb-dev \
# --rm \
#    	elkarbackup:deb
#

FROM ubuntu:16.04
MAINTAINER Xabi Ezpeleta <xezpeleta@gmail.com>

# Install required dependencies (git included)
RUN apt-get update && apt-get -y install \
    git \
    curl \
    acl \
    lintian \
    fakeroot \
    zip \
    unzip \
    php-cli \
    php-xml \
    && rm -rf /var/lib/apt/lists/*

COPY entrypoint.sh /
RUN chmod u+x /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]
