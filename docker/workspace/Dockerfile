FROM php:cli

RUN set -xe; \
    apt-get update -yqq && \
    apt-get install -yqq \
    apt-utils \
    npm \
    git \
    vim \
    zip \
    unzip \
    htop \
    procps \
    zlib1g-dev \
    libpng-dev \
    libzip-dev && \
    apt autoremove -yqq

RUN docker-php-ext-install \
    zip \
    pdo \
    pdo_mysql \
    mbstring \
    gd

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && \
php -r "if (hash_file('sha384', 'composer-setup.php') === 'a5c698ffe4b8e849a443b120cd5ba38043260d5c4023dbf93e1558871f1f07f58274fc6f4c93bcfd858c6bd0775cd8d1') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;" && \
php composer-setup.php --install-dir=/usr/local/bin --filename=composer && \
php -r "unlink('composer-setup.php');"

RUN npm install npm@latest -g