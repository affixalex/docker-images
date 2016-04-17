FROM hypoalex/alpine-consul-base:latest

RUN apk add --update python3 make && \
    rm -rf /var/cache/apk/*

ADD root /
ADD app /app

VOLUME ["/data/consul"]

EXPOSE 4000:4000