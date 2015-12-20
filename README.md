# docker-symfony

Developing a symfony2 project using docker

## Prerequisites

* If you're running boot2docker, make sure it's running with 2 CPUs, otherwise the container `application` will fail compiling (since ant requires openjre, and openjre doesn't work with a single CPU) => [https://github.com/docker/docker/issues/18180]()
* (Optional) Create your own server.crt and server.key

## Installation

* Clone this project `git clone git@github.com:slipke/docker-symfony.git`
* Copy the `docker` folder and `docker-compose.yml` into your symfony2 project, next to the `app` and `src` folder
* (Optional) If you want to use https://, copy your server.crt and server.key files into the `docker/nginx` folder, uncomment the specific `server { listen 443; ...}` part in the html.conf and uncomment the `ADD server.key` and `ADD server.crt` directives in the nginx `Dockerfile`
* Run `docker-compose up`, or to deamonize `docker-compose up -d`

## Usage

### Run symfony commands

Example command:

`docker-composer run application php app/console cache:clear --env=prod`

To make things easier use an alias:

`alias app="docker-composer run application"`

## Credits

Inspiration by

* [http://vincent.composieux.fr/article/run-a-symfony-application-using-docker-and-docker-compose]()
* [https://github.com/denderello/symfony-docker-example]()
* [http://geoffrey.io/making-docker-commands.html]()