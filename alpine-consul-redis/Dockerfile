FROM hypoalex/alpine-consul-base:latest


# Install redis
RUN apk add --update redis && \
    rm -rf /var/cache/apk/* && \
    mkdir -p /data/redis && \
    chown -R redis:redis /data/redis && \
    echo -e "include /etc/redis-local.conf\n" >> /etc/redis.conf

ADD root /

VOLUME ["/data/redis"]

EXPOSE 6379

