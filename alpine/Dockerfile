FROM 3bdigital/ci-tools:alpine

WORKDIR /root/

# Add PHP and Node
RUN apk update \
 && apk add --no-cache \
            php \
            php-dom \
            php-gd \
            php-pdo \
            php-session \
            php-simplexml \
            php-tokenizer \
            php-xml \
            php-xmlreader \
            php-xmlwriter \
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