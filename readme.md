# docker-images
My custom Docker images

## Wordpress
> https://github.com/atillay/wordpress-starter
```
$ docker build -t atillay/wordpress ./wordpress
$ docker push atillay/wordpress

$ docker build --build-arg PHP_VERSION=7.4 -t atillay/wordpress:7.4 ./wordpress
$ docker push atillay/wordpress:7.4

$ docker build --build-arg PHP_VERSION=7.3 -t atillay/wordpress:7.3 ./wordpress
$ docker push atillay/wordpress:7.3
```

## CraftCMS 3
> https://github.com/atillay/craftcms3-docker
```
$ docker build -t atillay/craftcms3-nginx ./craftcms3/nginx
$ docker push atillay/craftcms3-nginx
```
```
$ docker build -t atillay/craftcms3-php ./craftcms3/php
$ docker push atillay/craftcms3-php
```

## LEMP
> https://github.com/atillay/docker-lemp
```
$ docker build -t atillay/lemp-nginx ./lemp/nginx
$ docker push atillay/lemp-nginx
```
```
$ docker build -t atillay/lemp-php ./lemp/php
$ docker push atillay/lemp-php

$ docker build --build-arg PHP_VERSION=7.4 -t atillay/lemp-php:7.4 ./lemp/php
$ docker push atillay/lemp-php:7.4

$ docker build --build-arg PHP_VERSION=7.3 -t atillay/lemp-php:7.3 ./lemp/php
$ docker push atillay/lemp-php:7.3

$ docker build --build-arg PHP_VERSION=7.2 -t atillay/lemp-php:7.2 ./lemp/php
$ docker push atillay/lemp-php:7.2
```