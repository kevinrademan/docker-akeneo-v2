# docker-akeneo-v2
Docker container for the new V2 release of Akeneo



# docker-akeneo-v2

## Prerequisite

* [Docker compose](https://docs.docker.com/compose/)
* [token Github](https://github.com/settings/tokens)

## Enviroment variables

* MYSQL_HOST: mysql host string (default: mysql)
* MYSQL_DATABASE: mysql database name
* MYSQL_USER: mysql username
* MYSQL_PASSWORD: mysql password
* MONGO_LINK: host pour mongo (default: mongo)
* MONGO_DATABASE: base mongodb
* GITHUB_TOKEN: Token github pour installation via composer


## Images

* **akeneo**: installation of akeneo v2 with *MySQL* and *Elasticsearch*. [Readme](https://github.com/kevinrademan/docker-akeneo-v2/blob/master/akeneo/Readme.md)
    
## Interface

* Login initial: admin / admin