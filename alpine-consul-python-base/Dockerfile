FROM hypoalex/alpine-consul-base:latest

# Install Node.js, and the latest version of npm 
# (and Python in case any npm modules require building)
RUN apk add --update python3 make && \
    rm -rf /var/cache/apk/*

ADD root /
ADD app /app

VOLUME ["/data/consul"]

EXPOSE 4000:4000