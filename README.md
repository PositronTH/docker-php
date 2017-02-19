# PHP-FPM Image
My Docker Images

[NGINX](https://github.com/PositronTH/docker-nginx) -> [PHP-FPM](https://github.com/PositronTH/docker-php) -> [MONGO](https://github.com/PositronTH/docker-mongo) / [MEMCACHED](https://github.com/PositronTH/docker-memcached)

## Dockerfile
[positron/php](https://github.com/PositronTH/docker-php/blob/master/Dockerfile), [positron/php:7](https://github.com/PositronTH/docker-php/blob/master/Dockerfile), [positron/php:7.1](https://github.com/PositronTH/docker-php/blob/master/Dockerfile), [positron/php:latest](https://github.com/PositronTH/docker-php/blob/master/Dockerfile)

## How to use
Network Mode = host
**docker-compose**
```yaml
  php:
    container_name: "php"
    build: docker/php
    environment:
      - PHP_TIMEZONE=Asia/Bangkok
      - PHP_PORT=9000
      - PHP_STATUS_URL=/status
    restart: always
    privileged: true
    volumes:
      - /var/www:/var/www
    network_mode: "host"
```

# Package
- Centos 7
- PHP with FPM 7.1 (Remi's RPM repository)
ext:  php-common php-cli php-process php-pear php-pecl-memcache php-gd php-mbstring php-pecl-zip php-mcrypt php-xml php-pecl-apc php-pecl-mongodb php-xmlrpc php-opcache php-fpm
-  ImageMagick

.

# Note
** build **
```
sudo docker build -t positron/php -t positron/php:7 -t positron/php:7.1 -t positron/php:latest /home/positron/My/Webs/docker/php/
```
** push **
```
sudo docker push positron/php
```

.

for Jarm.com's Server
https://jarm.com
