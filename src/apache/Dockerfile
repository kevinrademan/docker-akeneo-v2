# Akeneo Web
FROM debian:stretch
LABEL maintainer "Kevin Rademan <kevin@versa.co.za>"

# Base + Akeneo requirements
RUN apt-get update \
    && apt-get install --no-install-recommends --yes \
        gnupg \
        apt-transport-https \
        ca-certificates wget \
    && wget -O /etc/apt/trusted.gpg.d/php.gpg https://packages.sury.org/php/apt.gpg \
    && sh -c 'echo "deb https://packages.sury.org/php/ stretch main" > /etc/apt/sources.list.d/php.list' \
    && apt-get update \
    && apt-get install --no-install-recommends --yes \
        openssh-client \
		curl \
		nano \
		git \
        apache2 \
        php7.1-apcu \
        php7.1-bcmath \
        php7.1-cli \
        php7.1-curl \
        php7.1-fpm \
        php7.1-gd \
        php7.1-intl \
        php7.1-mcrypt \
        php7.1-mysql \
        php7.1-soap \
        php7.1-xml \
        php7.1-zip \
        php7.1-imagick \
    && apt-get clean \
	&& rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Node
RUN curl -sL https://deb.nodesource.com/setup_8.x | bash - \
    && apt-get install -y nodejs

# Yarn
RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - \
    &&  echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list \
    && apt-get update && apt-get install yarn
	
# Apache
COPY config/000-default.conf /etc/apache2/sites-available/000-default.conf
RUN a2enmod rewrite proxy_fcgi

# Composer
RUN curl -sS https://getcomposer.org/installer | php -- --filename=composer --install-dir=/usr/local/bin

# PHP
COPY config/php.ini /etc/php/7.1/fpm/php.ini
COPY config/php.ini /etc/php/7.1/cli/php.ini

VOLUME /var/www/html
EXPOSE 80

COPY scripts/entrypoint.sh /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]

CMD ["apache2", "-D", "FOREGROUND"]