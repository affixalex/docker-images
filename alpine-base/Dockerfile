FROM alpine:3.3

ENV S6_OVERLAY_VERSION=v1.17.1.1
ENV GODNSMASQ_VERSION=0.9.8

# Add commonly used packages
RUN apk add --update bind-tools && \
    rm -rf /var/cache/apk/*

# Add S6 overlay
ADD https://github.com/just-containers/s6-overlay/releases/download/${S6_OVERLAY_VERSION}/s6-overlay-amd64.tar.gz /tmp/
RUN tar xzf /tmp/s6-overlay-amd64.tar.gz -C /
ADD https://github.com/janeczku/go-dnsmasq/releases/download/${GODNSMASQ_VERSION}/go-dnsmasq-min_linux-amd64 /usr/sbin/go-dnsmasq
RUN chmod +x /usr/sbin/go-dnsmasq

ADD root /

ENTRYPOINT ["/init"]
CMD []
