FROM alpine:3.9@sha256:b3dbf31b77fd99d9c08f780ce6f5282aba076d70a513a8be859d8d3a4d0c92b8

LABEL maintainer "Leonardo Gatica <lgatica@protonmail.com>"

ENV GIDDYUP_VERSION=0.19.0

RUN mkdir -p /opt/redis
COPY scripts /opt/redis/scripts
RUN apk add --no-cache curl && \
  mkdir -p /usr/local/etc/redis && \
  curl -o /usr/local/etc/redis/redis.conf http://download.redis.io/redis-stable/redis.conf && \
  curl -o /usr/local/etc/redis/sentinel.conf http://download.redis.io/redis-stable/sentinel.conf && \
  curl -sL -o /opt/redis/scripts/giddyup https://github.com/rancher/giddyup/releases/download/v${GIDDYUP_VERSION}/giddyup && \
  chmod +x /opt/redis/scripts/*
