# PHP-FPM Image
My Docker Images

[NGINX](https://hub.docker.com/r/positron/nginx) -> [PHP-FPM](https://hub.docker.com/r/positron/php) -> [MONGO](https://hub.docker.com/r/positron/mongo) / [MEMCACHED](https://hub.docker.com/r/positron/memcached)

## Dockerfile
[positron/php](https://github.com/positronth/docker-php/blob/master/Dockerfile), [positron/php:7](https://github.com/positronth/docker-php/blob/master/Dockerfile), [positron/php:7.1](https://github.com/positronth/docker-php/blob/master/Dockerfile), [positron/php:latest](https://github.com/positronth/docker-php/blob/master/Dockerfile)

## How to use
Network Mode = host

**docker-compose**
```yaml
  php:
    container_name: "php"
    image: positron/php
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
**build**
```
sudo docker build -t positron/php -t positron/php:7 -t positron/php:7.1 -t positron/php:latest /home/positron/My/Webs/.docker/php/ --no-cache=true
```
**push**
```
sudo docker push positron/php
```

.

for Jarm.com's Server
https://jarm.com
