# Docker Volumes

## Run mysql container
```bash

* docker pull mysql

* docker run -d -e MYSQL_ROOT_PASSWORD=root mysql:latest

```
## To make interactive with mysql container
```bash
* docker exec -it <container_id> bash

```
## To enter mysql database in the container
```bash
* mysql -u root -p
```
## To show database
```bash
* show databases;
```
## To create database
```bash
* create database KYC;

* use KYC;

* exit
```
## Stop and Remove MySQL container
```bash
* docker stop <container_id> && docker rm <container_id>
```
### After that if we run MySQL container again we cant see KYC database so Docker Volume comes to the picture


