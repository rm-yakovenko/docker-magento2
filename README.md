# Docker Magento2 ![](https://api.travis-ci.org/rm-yakovenko/docker-magento2.svg?branch=master)

Ready to run docker containers for Magento2.

## Getting started

1. Copy `.env.dist` to `.env`.
1. Configure `.env` if you need.
1. Copy `.env`, `docker` and `docker-compose.yml` to your magento2's root folder.
1. Run `docker-compose up -d`.
1. Open in your browser http://localhost:8080/ to access Magento2.
1. Open in your browser http://localhost:8081/ to access PhpMyAdmin.

## Useful tips

### Running composer install

```sh
docker/console composer install
```

### Running commands

```sh
docker/console bin/magento cache:clear
```

### Get into the container

```sh
docker/console bash
```
