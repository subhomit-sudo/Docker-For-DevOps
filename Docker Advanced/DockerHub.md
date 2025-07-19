# How to push an image to DockerHub

## Create DockerHub Account

* https://login.docker.com

## login in DockerHub by giving username and PAT

* docker login

## Build Docker image in local 

* docker build -t python-app-mini:latest -f ./Dockerfile-multi-stage  .

## Tag the docker image

* docker image tag python-app-mini:latest subhomit/python-app-mini:latest

## Check the tagged image

* docker images

## Push that image to DockerHub

* docker push subhomit/python-app-mini:latest
