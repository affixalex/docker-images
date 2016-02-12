FROM hypoalex/alpine-consul-base:latest

# Install Node.js, and the latest version of npm 
# (and Python in case any npm modules require building)
RUN apk add --update nodejs git python make && \
    rm -rf /var/cache/apk/* && \
    npm install -g npm

ADD root /
ADD app /app

VOLUME ["/data/consul"]

EXPOSE 4000:4000
