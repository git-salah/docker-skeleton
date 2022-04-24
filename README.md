# Docker skeleton
Template for making local sylius environment with Docker over Postgresql and Nginx server.

# Usage
To get started, make sure you have Docker installed on your system, and then clone this repository.

- Update `docker-compose.yml` with your db Credentials
- Create your project files inside the `src/app` directory.
- Update the `parameters.yml` file.
```
database_host: db  <<- (Docker service name)
database_port: 3306
database_name: maestro
database_user: root
database_password: root

env(SYLIUS_DATABASE_HOST): db
env(SYLIUS_DATABASE_PORT): 3306
env(SYLIUS_DATABASE_NAME): zvendo
env(SYLIUS_DATABASE_USER): root
env(SYLIUS_DATABASE_PASSWORD): root

maestro_database_host: db

```


In your terminal, navigate to the directory you cloned this repo, and spin up the containers for the web server by running 

```
sudo docker-compose up -d --build
```

To execute any command you have to write it inside its container 
for example, if you want to know the php version you will execute it inside the php container.
```
sudo docker-compose exec php php --version
```

# Ports
nginx      => :8000

mysql      => :3307

php        => :9000

phpmyadmin => :8081

redis      => :6379
