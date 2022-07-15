# Local Docker Environment Setup

This repo will walk you through setting up your local computer so you can write and test a Laravel application using
human friendly urls.

We'll also show you how to create and use SSL certificates on your Mac. The base container is hosted here:
https://hub.docker.com/r/brandondbest/laravel-web

For dev, pre-production and production environments, I recommend you use the Laravel Octane container:
https://hub.docker.com/r/brandondbest/laravel-octane

# Manual Setup

## Prerequisites

Please have the latest verion of Docker installed and running locally before you begin.

## Nginx Proxy

This is designed for setting up a local environment to test and run code. Ngixn proxy allows you to use human friendly
urls instead of remembering ports.
https://hub.docker.com/r/jwilder/nginx-proxy


### Nginx Proxy Setup

Copy nginx-proxy to your local computer:

```
mkdir ~/Sites/_packages;
mkdir ~/Sites/_packages/nginx-proxy;
mkdir ~/Sites/_packages/docker-local;
cd ~/Sites/_packages;
curl https://github.com/brandonbest/docker-local/archive/refs/tags/v1.0.0.zip --output docker-local/local-setup.zip;
unzip ./docker-local/local-setup.zip;
cp -R ./docker-local/nginx-proxy/* ./nginx-proxy;
rm -rf ~/Sites/_packages/docker-local;
```

Create a Docker Network:

```
docker network create nginx-proxy
```

Then change directories into nginx-proxy and run:

```
cd ~/Sites/_packages/docker-local;
docker-compose up -d;
```


### Nginx Proxy and SSL

Coming in the future - SSL Setup


## Laravel Setup

This step will setup a local Docker container with nginx proxy.

```
mkdir ~/Sites/_packages/nginx-proxy;
mkdir ~/Sites/docker-local.brandonbest.com;
cd ~/Sites/_packages;
curl https://github.com/brandonbest/docker-local/archive/refs/tags/v1.0.0.zip --output docker-local/local-setup.zip;
unzip ./docker-local/local-setup.zip;
cp -R ./docker-local/_deploy/* ~/Sites/docker-local.brandonbest.com;
rm -rf ~/Sites/_packages/docker-local;
```

## MySQL Setup

This step will setup a local MySQL container.

```
mkdir ~/Sites/_packages;
mkdir ~/Sites/_mysql/data;
cd ~/Sites/_packages;
curl https://github.com/brandonbest/docker-local/archive/refs/tags/v1.0.0.zip --output docker-local/local-setup.zip;
unzip ./docker-local/local-setup.zip;
cp -R ./docker-local/mysql ~/Sites/_mysql;
rm -rf ~/Sites/_packages/docker-local;
```

## Redis Setup

This step will setup a local Redis container.

```
mkdir ~/Sites/_packages;
mkdir ~/Sites/_redis/data;
cd ~/Sites/_packages;
curl https://github.com/brandonbest/docker-local/archive/refs/tags/v1.0.0.zip --output docker-local/local-setup.zip;
unzip ./docker-local/local-setup.zip;
cp -R ./docker-local/redis ~/Sites/_redis;
rm -rf ~/Sites/_packages/docker-local;
```