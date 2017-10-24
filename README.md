# docker-akeneo-v2
Docker container for the new V2 release of Akeneo

## Prerequisite
* [Docker compose](https://docs.docker.com/compose/)
* [token Github](https://github.com/settings/tokens)

## Enviroment variables
Make a copy of the .env.dist and rename it to .env.
Ensure that the following variables are set to your prefrence

* MYSQL_HOST: mysql host string (default: mysql)
* MYSQL_DATABASE: mysql database name (default: akeneo_pim)
* MYSQL_USER: mysql username  (default: akeneo_pim)
* MYSQL_PASSWORD: mysql password  (default: akeneo_pim)
* GITHUB_TOKEN: Token used by composer will installing packages composer (required!)

## Commands
Run these docker-compose commands from the /src folder
* Start container: docker-compose up
* Stop container: Hit Ctrl-C while its running
* Delete containers: docker-compose down
* Rebuild apache container: docker-compose build
    
## Interface
* Login initial: admin / admin


## Thanks
@s7b4 for the great Akeneo 1.7 containers
https://github.com/s7b4/docker-akeneo
