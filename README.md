# docker-laravel-postgres-nginx
Simple docker-compose for Laravel, with mysql, reddis, nginx and php-fpm
# Pre-requisites
* Docker running on the host machine.
* Docker compose running on the host machine.
* Basic knowledge of Docker.
 

# Installation
+ To get started, the following steps needs to be taken:
+ Clone the repo.
+ `cd laravel_docker` to the project directory.
+ `cd` to web and run the command to create a new Laravel project into **application** directory.
+ `cd ..` to back the project directory.
+ `cp .env.example .env` to use env config file
+ Run `docker-compose up -d` to start the containers.
+ Visit http://localhost:2502 to see your Laravel application.

# usage:
+ `docker-compose up -d` to start all containers
+ `docker-compose down` to stop all containers
+ If you need to restart after modifying *docker-compose.yml* restart with `docker-compose down` and `docker-compose up -d`

# Images
+ redis:alpine
+ nginx:alpine
+ php71-fpm:latest

# SourceFiles

## Into **sourcefiles** directory, exists others directories: **php-fpm** and **nginx**:


### nginx: nginx.conf
+ file conf nginx

### volumes:
- nginx folder
- php-ini-overrides.ini
- data(postgres)

### multiple servers:
- create file conf of nginx in nginx directory you should use default.conf as exemple 
- restart containers: `docker-compose down` and `docker-composer up -d`


# Troubleshooting

## If you need to restart after modifying *Dockerfile* and have Troubleshooting:
+ Verify all containers running: `docker ps -a`
+ Stop all containers and remove: `docker stop $(docker ps -a -q)` and `docker rm $(docker ps -a -q)`
+ Try to start again `docker-compose up -d`


