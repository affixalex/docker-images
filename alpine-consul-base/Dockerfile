FROM hypoalex/alpine-base:latest

ENV GOPATH=/go GOMAXPROCS=2
ENV CONSUL_VERSION=0.6.4
ENV XC_ARCH="amd64"
ENV XC_OS="linux"

# Download and install Consul and Consul Template
# We are building it ourselves, because Alpine Linux doesn't use glibc
RUN apk add --update ca-certificates go git gcc musl-dev make bash zip && \
    go get github.com/hashicorp/consul && \
    export PATH=$GOPATH/bin:$PATH && \
    cd /go/src/github.com/hashicorp/consul && \
    git checkout -q --detach "v$CONSUL_VERSION" && \
    make && \
    mv $GOPATH/bin/consul /bin && \
    rm -rf $GOPATH && \
    apk del go git gcc musl-dev make bash zip && \
    rm -rf /var/cache/apk/*  && \
    addgroup consul && \
    adduser -D -G consul consul && \
    mkdir -p /data/consul && \
    chown -R consul:consul /data/consul

#ADD https://releases.hashicorp.com/consul-template/0.12.2/consul-template_0.12.2_linux_amd64.zip /tmp 
#RUN unzip /tmp/consul-template_0.12.2_linux_amd64.zip -d /bin

ENTRYPOINT ["/init"]
