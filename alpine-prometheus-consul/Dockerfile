FROM hypoalex/alpine-base:latest

ADD https://github.com/prometheus/prometheus/releases/download/0.18.0rc1/prometheus-0.18.0rc1.darwin-amd64.tar.gz /tmp/
RUN tar xzf /tmp/

ADD root /

ENTRYPOINT ["/init"]
CMD []