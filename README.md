# Docker Datomic

[![Docker Pulls](https://img.shields.io/docker/pulls/akiel/datomic-free.svg)](https://hub.docker.com/r/pvgomes/datomic/)


## Setup

To start a container with Docker

    docker run -d -e ADMIN_PASSWORD="admin" -e DATOMIC_PASSWORD="datomic" -p 4334-4336:4334-4336 --name datomic-free pvgomes/datomic

You can access your databases through this URIs

    datomic:free://localhost:4334/<DB_NAME>?password=datomic
