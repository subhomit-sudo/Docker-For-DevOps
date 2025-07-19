# How to push an image to DockerHub

## Step:1 Create DockerHub Account

* https://login.docker.com

## Step:2 login in DockerHub by giving username and PAT

* docker login

## Step:3 Build Docker image in local 

* docker build -t python-app-mini:latest -f ./Dockerfile-multi-stage  .

## Step:4 Tag the docker image

* docker image tag python-app-mini:latest subhomit/python-app-mini:latest

## Step:5 Check the tagged image

* docker images

## Step:6 Push that image to DockerHub

* docker push subhomit/python-app-mini:latest
