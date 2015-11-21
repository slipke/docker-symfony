# docker-symfony

Developing a symfony2 project using docker

## Installation

* Clone this project `git clone git@github.com:slipke/docker-symfony.git`
* Copy the `docker` folder and `docker-compose.yml` into your symfony2 project, next to the `app` and `src` folder
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