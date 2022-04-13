# Docker-skeleton
Template for making local syius environment with Docker over Postgresql and Nginx server.

# Usage
To get started, make sure you have Docker installed on your system, and then clone this repository.

- Update `docker-compose.yml` by replacing `{{app-name}}` , `{{db-name}}` with your app and db names
- Create your project inside the `src` directory.
- Update the `.env` file.
```
DB_CONNECTION=pgsql
DB_HOST=postgres    //The container name inside the docker-compose file
DB_PORT=5432
DB_DATABASE=your_db
DB_USERNAME=root
DB_PASSWORD=root
```


In your terminal, navigate to the directory you cloned this repo, and spin up the containers for the web server by running 

```
docker-compose up -d
```

To execute any command you have to write it inside its container 
for example, if you want to run the migrations you will execute it inside the php container.
```
docker-compose exec php php artisan migrate
```

# Ports
nginx      => :8060

postgres   => :3000

php        => :9000

pgadmin    => :82
