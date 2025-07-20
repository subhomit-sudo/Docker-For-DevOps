# Docker Compose

## Install Docker Compose
```bash
* apt-get install docker-compose-v2

```
## Write Docker-Compose in yml
```yaml
services:
  mysql:
    image: mysql:5.7
    container_name: mysql
    environment:
      MYSQL_ROOT_PASSWORD: admin
      MYSQL_DATABASE: my_db
      MYSQL_USER: admin
      MYSQL_PASSWORD: admin
    volumes:
      - ./mysql-data:/var/lib/mysql
      - ./message.sql:/docker-entrypoint-initdb.d/message.sql  
    networks:
      - twotier
    healthcheck:
      test: ["CMD", "mysqladmin", "ping", "-h", "localhost", "-uadmin", "-padmin"]
      interval: 10s
      retries: 5
      start_period: 60s
      timeout: 5s

  flask-app:
    build:
      context: .
    container_name: flask-app
    ports:
      - "5000:5000"
    environment:
      MYSQL_HOST: mysql
      MYSQL_USER: admin
      MYSQL_PASSWORD: admin
      MYSQL_DB: my_db
    depends_on:
      - mysql
    networks:
      - twotier
    restart: always

networks:
  twotier:
```
