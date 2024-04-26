# DockStack

This project includes different Docker Compose configurations for various development stacks (sql databases, nosql databases and mail server) and resources to simplify the initiation of development and web development. Each stack is located in a separate directory, and the data of the services are persisted using Docker volumes.


## Stacks

-   **Postgres**: Contains a configuration for A PostgreSQL database provider and PgAdmin. To Host Sql databases.

-   **MySQL**: Contains a configuration for A MySQL database provider and phpMyAdmin. To Host Sql databases.

-   **MongoDB**: Contains a configuration for A MongoDB database provider and Mongo Express. To Host NoSql databases.

-   **Redis**: Contains a configuration for A Redis database provider and Redis Commander. To Host NoSql databases ued mainly for caching.

-   **MailHog**: Contains a configuration for A MailHog SMTP server. To Host a Mail server.

-   **SqlServer**: Contains a configuration for A Microsoft SQL Server database provider and Adminer. To Host Sql databases.


## Usage

1. Install Docker and Docker Compose.
2. Clone this repository.
3. Navigate to the directory of the stack you want to use. For example, if you want to use the Postgres stack, run the following command:

```sh
    cd Postgres
```

-   You can change the configuration in the environment file (.env) or directly in the docker-compose.yml file
-   Some services don't have the restart policy set to always. You can change it in the docker-compose.yml file.

4. Run the following command to start the service:

```sh
    docker-compose up # You can add the -d flag to run the containers in the background
```

5. Your service should be accessible with the correct configuration. To check on the service status, run the following command:

```sh
    docker-compose ps
```

6. To take down the service, run the following command:

```sh
    docker-compose down # You can add the -v flag to remove the volumes as well and the --rmi all flag to remove the images as well
```


## Default Configuration

Postgres service

```
postgres host: localhost
port: 5432
username: postgres
password: postgres

PgAdmin: localhost:8080
email: admin@admin.com
password: admin

postgres-data volume to persist data
```

MySQL service

```
mysql host: localhost
port: 3306
username: root
password: root

PhpMyAdmin: localhost:8081

mysql-data volume to persist data
```

MailHog service

```
host: localhost
port: 1025
username: null
password: null
```

MongoDB service

```
host: localhost
port: 27017
username: admin
password: admin

Mongo Express: localhost:8082
username: admin
password: admin

mongo-data volume to persist data
```

Redis service

```
host: localhost
port: 6379
username: null
password: null

Redis Commander: localhost:8083

redis-data volume to persist data
```

SqlServer service

```
host: localhost
port: 5434
username: sa
password: password_123

Adminer: localhost:8084

mssql-data volume to persist data
```

## Note

Remember to change the default passwords and other sensitive information before deploying in a production environment.


## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
