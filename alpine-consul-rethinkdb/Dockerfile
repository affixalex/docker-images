FROM hypoalex/alpine-consul-base

# Install RethinkDB
RUN apk add rethinkdb --update-cache \
    --repository http://dl-3.alpinelinux.org/alpine/edge/testing/ \
    --allow-untrusted

ADD root /

#    process cluster webui
EXPOSE 28015 29015 8080
