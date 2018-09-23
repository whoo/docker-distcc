#FROM gentoo/stage3-amd64
FROM scratch
MAINTAINER Dominique DERRIER <derrierdo@gmail.com>
### Files 
#ADD http://distfiles.gentoo.org/releases/amd64/autobuilds/20180920T214502Z/stage3-amd64-20180920T214502Z.tar.xz
ADD stage3-amd64-*tar.xz /
ADD make.conf /etc/portage/
RUN emerge --sync  >/dev/null
ENV EMERGE_DEFAULT_OPTS "--with-bdeps y --backtrack 30 --quiet-build=y"
RUN emerge ncdu distcc @world
RUN emerge --depclean
RUN rm /usr/portage/* -rf
RUN rm /tmp/* -rf
