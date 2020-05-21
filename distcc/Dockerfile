FROM alpine AS builder
RUN apk add --update wget
RUN wget https://bouncer.gentoo.org/fetch/root/all/releases/amd64/autobuilds/20200516T183750Z/stage3-amd64-20200516T183750Z.tar.xz
RUN mkdir /dd ; cd /dd; tar -Jxf /stage3-amd64-*.tar.xz

# Emerge
FROM scratch AS build2
COPY --from=builder /dd /
ADD make.conf /etc/portage/
RUN emerge --sync
ENV EMERGE_DEFAULT_OPTS "--with-bdeps y --backtrack 30 --quiet-build=y"
RUN emerge -uDN ncdu distcc @world 
RUN emerge --depclean
RUN rm /usr/portage/* /tmp/* -rf

# Clean 
FROM scratch
MAINTAINER Dominique DERRIER <derrierdo@gmail.com>
COPY --from=build2 / /

