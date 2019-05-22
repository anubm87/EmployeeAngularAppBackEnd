# Employee DB

## Introduction-Docker
Docker is a Linux container management toolkit with a "social" aspect, allowing users to publish container images and consume those published by others. A Docker image is a recipe for running a containerized process, and in this guide we will build one for a simple Spring boot application.

You will also need Docker, which only runs on 64-bit machines. See https://docs.docker.com/installation/#installation for details on setting Docker up for your machine. Before proceeding further, verify you can run docker commands from the shell. If you are using boot2docker you need to run that first.

## The Task Assigned...
Task was to create the docker image for the backend service.


#Add in build.gradle
bootJar {
    baseName = 'boot-docker'
    //version =  '0.1.0'
}

##Dockerfile
FROM openjdk:11
ADD build/libs/boot-docker.jar boot-docker.jar
EXPOSE 8080
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","/boot-docker.jar"]

## Command
* when the bradle builds succesfully,generates the jar file under build/libs
*go to docker terminal execute ::::docker build -f Dockerfile -t boot-docker.jar .
*Upon succesful build,docker creates image under boot-docker
*you can check images using command:::Docker images ls
*Run the docker image as
    docker run -p 8080:8080 boot-docker
*Now its deployed to server and you opens up on successful connection with DB.


## How to submit your work
* Push to your cloned github repository.
* Make a pull request back to the original master.

 
