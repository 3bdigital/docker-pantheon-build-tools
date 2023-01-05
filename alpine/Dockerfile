FROM 3bdigital/ci-tools:alpine

# Add PHP and Node
RUN apk update \
 && apk upgrade \
 && apk add --no-cache \
            php \
            php-dom \
            php-xml \
            composer \
            npm \
 && rm -rf /var/cache/apk/*

# Install Terminus
RUN mkdir -p ~/terminus \
  && cd ~/terminus \
  && curl -L https://github.com/pantheon-systems/terminus/releases/download/3.1.0/terminus.phar --output terminus \
  && chmod +x terminus \
  && ./terminus self:update \
  && ln -s ~/terminus/terminus /usr/local/bin/terminus