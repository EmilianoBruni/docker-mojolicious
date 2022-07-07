# # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # #
#
# AUTHORS :  Emiliano Bruni (EB) <info@ebruni.it>
# DATE    :  2022-07-07
# PURPOSE :
#   Minimum components to run [Mojolicious](https://mojolicious.org), a real-time web framework and web development toolkit written in [Perl](https://www.perl.org).
#
#   This image is published in docker hub with handle: ebruni/mojolicious
#
# USAGE:
#   docker build -t mojolicious .
#
# UPDATES:
#   AUTHOR  DATE        VER  COMMENTS
#   EB      2022-07-07  1.6  Add DBIC/mysql client support. Add tini package.
#   EB      2022-06-07  1.5  Update to Mojolicious v. 9.26
#   EB      2022-02-24  1.4  Update to Mojolicious v. 9.22
#   EB      2021-09-09  1.3  Add tags for Mojolicious::Plugin::Mongodbv2.
#   EB      2021-09-09  1.2  Removed Minion::Backend::MongoDB.
#   EB      2021-09-07  1.1  Update Minion::Backend::MongoDB to latest version.
#   EB      2021-08-23  1.0  Initial Version.
#
# # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # #
#

#
# this file is generated via docker-builder
#
# do not edit it directly
#
FROM alpine:3.14
MAINTAINER Emiliano Bruni <info@ebruni.it>

WORKDIR /var/www
EXPOSE 3000 8080

RUN apk update && apk add --no-cache \
    tini \
    make \
    gcc \
    perl-dev \
    perl-app-cpanminus \
    perl-module-build \
    perl-namespace-clean \
    perl-boolean \
    perl-json-maybexs \
    perl-test-fatal \
    perl-path-tiny \
    perl-moo \
    perl-file-find-rule \
    perl-number-compare \
    perl-text-glob \
    musl-dev \
  && cpanm --no-wget -n \
    Mojolicious \
  && rm -r /root/.cpanm \
 && apk add --no-cache \
&& cpanm --no-wget -n \
    Minion \
    Mojolicious::Plugin::Mongodbv2 \
  && rm -r /root/.cpanm \
  && apk del \
    make \
    gcc \
    perl-dev \
    musl-dev \
  && true

ARG NOW=not-set
LABEL org.opencontainers.image.authors="Emiliano Bruni <info@ebruni.it>"
LABEL org.opencontainers.image.created=$NOW
LABEL org.opencontainers.image.description="minimum components to run Mojolicious, a real-time web framework and web development toolkit written in Perl."
LABEL org.opencontainers.image.documentation=https://github.com/EmilianoBruni/docker-mojolicious/blob/master/README.pod
LABEL org.opencontainers.image.licenses=Artistic-2.0
LABEL org.opencontainers.image.source=https://github.com/EmilianoBruni/docker-mojolicious/blob/master/minion-mongodb/Dockerfile
LABEL org.opencontainers.image.title=docker-mojolicious
LABEL org.opencontainers.image.url=https://github.com/EmilianoBruni/docker-mojolicious
LABEL org.opencontainers.image.version=1.6-minion-mongodb

CMD ["/bin/bash", "-c"]
