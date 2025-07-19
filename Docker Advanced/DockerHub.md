# How to push and pull an image to DockerHub

## Step:1 Create DockerHub Account

```bash

* https://login.docker.com

```

## Step:2 login in DockerHub by giving username and PAT

```bash

* docker login

```

## Step:3 Build Docker image in local 

```bash

* docker build -t python-app-mini:latest -f ./Dockerfile-multi-stage  .

```

## Step:4 Tag the docker image

```bash

* docker image tag python-app-mini:latest subhomit/python-app-mini:latest

```

## Step:5 Check the tagged image

```bash

* docker images

```

## Step:6 Push that image to DockerHub

```bash

* docker push subhomit/python-app-mini:latest

```

## Step:7 Pull any image from DockerHub

```bash

* docker pull mysql

* docker pull subhomit/python-app-mini:latest

```
