# maven-spring-boot

Docker image that contains maven with lots of dependencies for spring boot projects. This should increase build speeds dramatically.

## Intro

This repo contains source to build Docker images that contain maven with lots of spring-boot related dependencies.

This repo is automatically connected to docker hub to build public docker images. 

## How to use

Refer to official [maven docker image](https://hub.docker.com/_/maven/) (usage is the same).

Most common use - run this command from the source of your spring boot source code:

```
mvn run --rm -v "$PWD":/sourcecode lukastosic/maven-spring-boot:1.5.3.RELEASE-3.5-jdk-8-alpine mvn clean package
```

Run parameters:

* `-v "$PWD":/sourcecode` - this will map your source code folder inside [working directory](https://docs.docker.com/engine/reference/builder/#workdir) of docker container

* `1.5.3.RELEASE-3.5-jdk-8-alpine` - this is the tag of docker image. This tag means that image is based on Spring Boot `1.5.3.RELEASE` and maven docker image tag `3.5-jdk-8-alpine`

* `mvn clean package` - this is just sample `mvn` command. You can execute any maven command that you want.
