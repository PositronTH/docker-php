# PHP-FPM Image
My Docker Images

[NGINX](https://hub.docker.com/r/positron/nginx) -> [PHP-FPM](https://hub.docker.com/r/positron/php) -> [MONGO](https://hub.docker.com/r/positron/mongo)

## Dockerfile  

7.2  
[positron/php:7.2](https://github.com/positronth/docker-php/blob/master/7.2/Dockerfile),

7.1  
[positron/php:7.1](https://github.com/positronth/docker-php/blob/master/7.1/Dockerfile),   

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
ext:  php-common php-cli php-process php-pear php-pecl-memcache php-gd php-mbstring php-pecl-zip php-mcrypt php-xml php-pecl-apc php-pecl-mongodb php-xmlrpc php-opcache php-fpm php-mysql
-  ImageMagick

.

# Note
**7.2**  
build  
```
docker build -t positron/php:7.2 /var/www/.docker/php/7.2/ --no-cache=true
```  
.  
push  
```
docker push positron/php:7.2
```  
.  

**7.1**  
build  
```
docker build -t positron/php -t positron/php:7 -t positron/php:7.1 -t positron/php:latest /var/www/.docker/php/7.1/ --no-cache=true
```  
.  
push  
```
docker push positron/php:7.1
```  
.  

for Jarm.com's Server
https://jarm.com
