# # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # #
#
# AUTHOR  :  Emiliano Bruni <info@ebruni.it>
# DATE    :  2021-07-28
# PURPOSE :
#   Minimum components to run [Mojolicious](https://mojolicious.org), a real-time web framework and web development toolkit written in [Perl](https://www.perl.org).
#
#   This image is published in docker hub with handle: ebruni/mojolicious
#
# USAGE:
#   docker build -t mojolicious .
#
# UPDATES:
#   AUTHOR          DATE        VERSION   COMMENTS
#   Emiliano Bruni  2021-08-23  1.0       Initial Version
#
# # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # #
#

#
# this file is generated via docker-builder
#
# do not edit it directly
#
FROM alpine:3.14 as builder
MAINTAINER Emiliano Bruni <info@ebruni.it>

WORKDIR /var/www
EXPOSE 3000 8080

RUN apk update && apk add --no-cache \
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
  && cpanm --no-wget \
    Mojolicious \
  && rm -r /root/.cpanm \
 && apk add --no-cache \
    musl-dev \
&& cpanm --no-wget \
    Minion \
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
LABEL org.opencontainers.image.description="Minimum components to run Mojolicious, a real-time web framework and web development toolkit written in Perl."
LABEL org.opencontainers.image.documentation=https://github.com/EmilianoBruni/docker-mojolicious/blob/master/README.pod
LABEL org.opencontainers.image.licenses=Artistic-2.0
LABEL org.opencontainers.image.source=https://github.com/EmilianoBruni/docker-mojolicious/blob/master/minion/Dockerfile
LABEL org.opencontainers.image.title=docker-mojolicious
LABEL org.opencontainers.image.url=https://github.com/EmilianoBruni/docker-mojolicious
LABEL org.opencontainers.image.version=1.0-minion

CMD ["/bin/bash", "-c"]
