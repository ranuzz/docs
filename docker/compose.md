# docker compose

command to run and manage multiple inter-dependant services with comman networking

## writing compose files

> sample file

```yaml
version: '2.1'
services:
    postgres:
        image: 'postgres:latest'
        environment:
            - POSTGRES_PASSWORD=secret
    webserver:
        image: local_image:tag
        restart: always
        depends_on:
            - postgres
        environment:
            - SQL_ALCHEMY_CONN=postgresql://postgres:secret@postgres:5432/postgres
        ports:
            - "8080:8080"
        command: webserver
        healthcheck:
            test: ["CMD-SHELL", "[ -f /usr/local/webserver.pid ]"]
            interval: 30s
            timeout: 30s
            retries: 3
```

* make sure that all required images are accessible
* local images are built and available `docker images`
* hub image tag are proper e.g. `postgres:latest`

> start writing compose file

* it is YAML file

* first line is version : `version: '2.1'` current version is 3+
* next start defining services using `service` tag
* child of service tags are services and first child is the service name `postgres` & `webserver` here, these names can be used in children as hostname wherever necessary as in `SQL_ALCHEMY_CONN`

* save the file `filename.yml`

## Running compose

```sh
docker-compose -f filename.yml up -d
```

## monitoring the services


* use kitematic
* or simple docker exec or logs `docker container ls`

## stopping services

```sh
docker-compose -f filename.yml down
```
