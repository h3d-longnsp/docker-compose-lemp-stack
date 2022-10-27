# Docker Compose LEMP Stack

This repository contains a little `docker-compose` configuration to start a `LEMP (Linux, Nginx, MySQL, PHP)` stack.

## Details

The following versions are used.

* php 8.1 (php-fpm) 
* nginx 1.23.2
* mysql-server 8.0
* phpMyAdmin 5.2

## Configuration

The configuration for each component could be found in corresponding folder in `/.docker/`.

You can also set the following environment variables, for example in the included `.env.example` file:

| Key | Description |
|-----|-------------|
|DOCKER_COMPOSE_NAME|The prefix before each container name when creating the containers.|
|MYSQL_ROOT_PASSWORD|The MySQL root password used when creating the containers.|

## Usage

To use it, simply follow the following steps:

##### Clone this repository.

Clone this repository.

##### Start the server.

Start the server in the background using the following command inside the cloned directory: `docker compose up -d`.

Go to `phpmyadmin.test` to access phpmyadmin page. Login using `root`/`MYSQL_ROOT_PASSWORD`.

To view aggregated logs of every containers, run: `docker compose logs -f`. To view logs of a specific container, run: `docker compose logs {SERVICE_NAME}`

##### Stop the server.

Stop the server using following command: `docker compose down`. To delete their volume, add `-v` option.

## Entering the containers

You can use the following command to enter a container where `{CONTAINER_NAME}` is in `docker ps`:

`docker exec -it {CONTAINER_NAME} bash`

