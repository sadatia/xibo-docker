# Xibo Docker

[Docker](https://docker.com/) is an application to package and run any
application in a pre-configured container making it much easier to deploy a Xibo
CMS with recommended configuration.

This repository holds the docker container definitions for Xibo and the docker-compose
configuration, which is used to bootstrap, start, stop and destroy the installation.

## Installation
First confirm that your traefik is running. The port 8082 is free. It that port is occupied by other app than change the port in docker-compose.yml file
## Running docker-compose
To run with the automation provided by docker-compose. 
use the command:
      docker-compose up -d

## Directory structure

This repository contains Docker configuration (Dockerfile) for the Xibo
containers. A normal installation *only* requires `docker-compose.yaml` and
a `config.env.template` file, suitably configured, saved as `config.env`.

#### /containers

web and xmr Dockerfiles and associated configuration. These are built by Docker
Hub and packaged into `xibosignage/xibo-cms` and `xibosignage/xibo-xmr`.

#### DATA_DIR/shared

Data folders for the Xibo installation.

 - The Library storage can be found in `/shared/cms/library`
 - The database storage can be found in `/shared/db`
 - Automated daily database backups can be found in `/shared/backup`
 - Custom themes should be placed in `/shared/cms/web/theme/custom`
 - Custom modules should be placed in `/shared/cms/custom`
 - Any user generated PHP or resources external to Xibo that you want hosted
   on the same webserver go in `/shared/cms/web/userscripts`. They will then
   be available to you at `http://localhost/userscripts/`



