# LEMP Server
LEMP Stack server using Docker Containers

## Requirements
- docker
- docker-compose

## Features
- PHP
- MySQL
- Nginx
- Phpadmin

## Exposed volumes
- DB
- Logs
- Nginx Configs

## Configuring PHP
You can configure PHP using Dockerfile in docker/php

## Initialization
- `docker-compose build`
- `docker-compose up`

## Connecting to the database

All databse data will be store in the `db` folder and it is already ignored but it is advised to store it for backup but not for version control.

- servername: mysql
- username: root
- password: 1234
- database name: db

## PHP server
- All files should be stored in the `www` folder.