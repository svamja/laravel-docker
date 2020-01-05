
# Overview

This is a "dockerized" version of a simple working laravel project.

* [Original Laravel Quickstart project](https://github.com/laravel/quickstart-basic)
* [Dockerization Guide by Brian Baliach](https://balysnotes.com/single_post/Brian_Baliach/051032437815811656) 

Below are the docker artifacts added to this project:
   
    docker-compose.yml (the master docker compose file to build three containers)
    .env.prod (this is copied to .env during build)
    development/.dockerignore (to ignore files to be copied during build)
    development/app.dockerfile (php + laravel container)
    development/web.dockerfile (nginx container)
    development/vhost.conf (nginx default host config file)

Note that mysql is a standard image and so no build file required for it.

## Prerequisites

* Docker Engine (or simply "docker" command line) [Ubuntu](https://docs.docker.com/v17.09/engine/installation/linux/docker-ce/ubuntu/)
* Docker Compose [Ubuntu](https://docs.docker.com/compose/install/)

## Steps to Run

    git clone https://github.com/svamja/laravel-docker
    cd laravel-docker
    docker-compose up -d --build
    docker-compose run app php artisan migrate

Alternatively, you can use build and up commands separately.

    docker-compose build
    docker-compose up -d

Or, you can build and run these containers separately:

    docker-compose build database
    docker-compose build app
    docker-compose build web
    docker-compose up -d database
    docker-compose up -d app
    docker-compose up -d web


## See the Result

Visit `http://localhost/` or `http://host.ip.addr/` to view a Task List application.


## Stopping

To stop the containers, simply run:

    docker-compose down

To delete the artifacts created by this project:

    docker-compose down --rmi all


