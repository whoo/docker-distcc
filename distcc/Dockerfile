FROM alpine:edge
MAINTAINER Dominique DERRIER <derrierdo@gmail.com>
RUN apk add --update distcc build-base
RUN ln /usr/bin/x86_64-alpine-linux-musl-g++ /usr/bin/x86_64-pc-linux-gnu-g++
RUN ln /usr/bin/x86_64-alpine-linux-musl-gcc /usr/bin/x86_64-pc-linux-gnu-gcc

