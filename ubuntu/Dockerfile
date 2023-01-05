FROM 3bdigital/ci-tools:ubuntu

ENV DEBIAN_FRONTEND=noninteractive

# Add PHP and Node
RUN apt-get update \
 && apt-get upgrade \
 && apt-get install -y software-properties-common \
 && add-apt-repository ppa:ondrej/php \
 && apt-get install -y \
            php8.1 \
            php8.1-xml \
            composer \
            npm \
 && rm -rf /var/lib/apt/lists/*

# Install Terminus
RUN mkdir -p ~/terminus \
  && cd ~/terminus \
  && curl -L https://github.com/pantheon-systems/terminus/releases/download/3.1.0/terminus.phar --output terminus \
  && chmod +x terminus \
  && ./terminus self:update \
  && ln -s ~/terminus/terminus /usr/local/bin/terminus