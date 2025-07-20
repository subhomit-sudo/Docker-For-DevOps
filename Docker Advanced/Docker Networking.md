# Docker Networking
```
If we have two docker container they have their own network so they cant talk to each other.
Thats what we need Docker Network.
```
## Types of Docker Networks
```
1. Bridge (default)
2. None
3. Host
4. User defined bridge
5. MacvLAN
6. IPvLAN
7. Overlay
```
## We will work with Two-tier-flask App
```baah
https://github.com/subhomit-sudo/two-tier-flask-app.git

```
## Navigate to the project directory
```
cd your-repo-name
```
## Create a .env file in the project directory to store your MySQL environment variables:
```
touch .env
```
## Open the .env file and add your MySQL configuration
```
MYSQL_HOST=mysql
MYSQL_USER=admin (your_username)
MYSQL_PASSWORD=admin (your_password)
MYSQL_DB=my_db (your_database)
```
## First create a docker image from Dockerfile
```
* docker build -t flask-app .
```
## Now, make sure that you have created a network using following command
```
* docker network create twotier
```
## Attach both the containers in the same network, so that they can communicate with each other
```
i) MySQL container

docker run -d \
    --name mysql \
    -v mysql-data:/var/lib/mysql \
    --network=twotier \
    -e MYSQL_DATABASE=my_db \
    -e MYSQL_PASSWORD=admin \
    -e MYSQL_USER=admin \
    -e MYSQL_ROOT_PASSWORD=admin \
    -p 3306:3306 \
    mysql:5.7

ii) Backend container

docker run -d \
    --name flaskapp \
    --network=twotier \
    -e MYSQL_HOST=mysql \
    -e MYSQL_USER=admin \
    -e MYSQL_PASSWORD=admin \
    -e MYSQL_DB=my_db \
    -p 5000:5000 \
    flask-app:latest
```

