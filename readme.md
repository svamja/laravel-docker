
# Introduction

This is a "dockerized" version of a simple working laravel project.

* [Original Laravel Quickstart project](https://github.com/laravel/quickstart-basic)
* [Dockerization Guide by Brian Baliach](https://balysnotes.com/single_post/Brian_Baliach/051032437815811656) 

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

To stop the containers, simply run:

    docker-compose down
    

## See the Result

Visit `http://localhost/` or `http://host.ip.addr/` to view a Task List application.

