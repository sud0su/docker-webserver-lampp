# Docker WebServer LAMP

## Requirements

Install [Docker](https://docs.docker.com/engine/installation) and [Docker Compose](https://docs.docker.com/compose/install).

## Installation

Clone this repository to your computer.

```console
sud0su@oprek$ git clone https://github.com/sud0su/docker-webserver-lampp.git
sud0su@oprek$ cd docker-webserver-lampp
```

- Start Server

```console
sud0su@oprek$ docker-compose up -d
```

- Check Container Running

```console
sud0su@oprek$ docker ps
```

- Stop Server

```console
sud0su@oprek$ docker-compose stop
```

## Web Server

#### Apache

Apache configured to run on default port `80`, so you can access it from `http://localhost`

#### PhpMyAdmin

PhpMyAdmin configured to run on port `8081`, so you can access it from `http://localhost:8081`

#### PHP & MySQL

This local server use `PHP Version 7.1.16` and `5.7.21-1debian9`

Please check `Dockerfile` at `dockerfile/apache/` to see an extensions that have installed. You can modify a dockerfile to add new extension as you want.