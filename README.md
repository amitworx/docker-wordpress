# WordPress Development Environment with Docker

This repository provides a WordPress development environment using Docker and Docker Compose. It sets up the following services:
- MySQL Database (`db`)
- phpMyAdmin (`phpmyadmin`)
- WordPress (`wordpress`)

This environment is ideal for local development and testing.

## Requirements

Before using this setup, ensure that you have the following installed on your local machine:
- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

## Getting Started

1. Clone this repository to your local machine:
   ```bash
   git clone <repository-url>
   cd <repository-directory>

2. Ensure that Docker is running on your machine.

3. Run the following command to start the containers:

    docker-compose up

4. Once the setup is complete, the following services will be available:

    WordPress: http://localhost:8000
    phpMyAdmin: http://localhost:8080
    You can log into phpMyAdmin using the following credentials:

    Username: user
    Password: root
    Server: db

Services Overview
1. MySQL (db)
Image: mysql:5.7
Container Name: db
Ports:
3306:3306 (mapped to host)
Environment Variables:
MYSQL_ROOT_PASSWORD: root
MYSQL_DATABASE: wp_db
MYSQL_USER: user
MYSQL_PASSWORD: password
Data Persistence: MySQL data is persisted in the ./db directory on the host machine.
2. phpMyAdmin (phpmyadmin)
Image: phpmyadmin/phpmyadmin
Container Name: phpmyadmin
Ports:
8080:80 (phpMyAdmin is accessible via http://localhost:8080)
Environment Variables:
PMA_HOST: db (MySQL container)
MYSQL_ROOT_PASSWORD: root
3. WordPress (wordpress)
Image: wordpress:latest
Container Name: wordpress
Ports:
8000:80 (WordPress is accessible via http://localhost:8000)
Environment Variables:
WORDPRESS_DB_HOST: db:3306
WORDPRESS_DB_USER: user
WORDPRESS_DB_PASSWORD: password
WORDPRESS_DB_NAME: wp_db
Data Persistence: WordPress files are persisted in the ./wordpress directory on the host machine.
Stopping the Environment
To stop the environment, press CTRL + C in the terminal where docker-compose up is running, or run the following command in another terminal:

docker-compose down


Certainly! Here's a README.md file for your WordPress development setup using Docker and Docker Compose:

markdown
Copy code
# WordPress Development Environment with Docker

This repository provides a WordPress development environment using Docker and Docker Compose. It sets up the following services:
- MySQL Database (`db`)
- phpMyAdmin (`phpmyadmin`)
- WordPress (`wordpress`)

This environment is ideal for local development and testing.

## Requirements

Before using this setup, ensure that you have the following installed on your local machine:
- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

## Getting Started

1. Clone this repository to your local machine:
   ```bash
   git clone <repository-url>
   cd <repository-directory>
Ensure that Docker is running on your machine.

Run the following command to start the containers:

bash
Copy code
docker-compose up
Once the setup is complete, the following services will be available:

WordPress: http://localhost:8000
phpMyAdmin: http://localhost:8080
You can log into phpMyAdmin using the following credentials:

Username: root
Password: root
Server: db
Services Overview
1. MySQL (db)
Image: mysql:5.7
Container Name: db
Ports:
3306:3306 (mapped to host)
Environment Variables:
MYSQL_ROOT_PASSWORD: root
MYSQL_DATABASE: wp_db
MYSQL_USER: user
MYSQL_PASSWORD: password
Data Persistence: MySQL data is persisted in the ./db directory on the host machine.
2. phpMyAdmin (phpmyadmin)
Image: phpmyadmin/phpmyadmin
Container Name: phpmyadmin
Ports:
8080:80 (phpMyAdmin is accessible via http://localhost:8080)
Environment Variables:
PMA_HOST: db (MySQL container)
MYSQL_ROOT_PASSWORD: root
3. WordPress (wordpress)
Image: wordpress:latest
Container Name: wordpress
Ports:
8000:80 (WordPress is accessible via http://localhost:8000)
Environment Variables:
WORDPRESS_DB_HOST: db:3306
WORDPRESS_DB_USER: user
WORDPRESS_DB_PASSWORD: password
WORDPRESS_DB_NAME: wp_db
Data Persistence: WordPress files are persisted in the ./wordpress directory on the host machine.
Stopping the Environment
To stop the environment, press CTRL + C in the terminal where docker-compose up is running, or run the following command in another terminal:

bash
Copy code
docker-compose down
This will stop and remove all containers.

Resetting the Environment
If you wish to reset the environment (clear the MySQL database and WordPress files), delete the ./db and ./wordpress directories, and then run the docker-compose up command again:

rm -rf ./db ./wordpress
docker-compose up

Customization
You can customize the environment by editing the docker-compose.yml file:

To change MySQL database credentials or settings, modify the db service.
To change WordPress configurations, modify the wordpress service.
Useful Commands
Start the environment:
docker-compose up
Stop the environment:
docker-compose down
Rebuild the environment after changes:
docker-compose up --build
View running containers:
docker ps
Access a running container's shell:
docker exec -it <container_name> /bin/bash

Replace <container_name> with db, phpmyadmin, or wordpress depending on the container you want to access.

Troubleshooting
If you encounter port conflicts, make sure the ports 3306, 8080, and 8000 are not being used by other services on your machine.
For phpMyAdmin, use the server db and root credentials (root as both username and password) to log in.
License
This project is open-source and available under the MIT License.


### Summary:
- This `README.md` provides clear instructions on setting up and using your WordPress development environment using Docker and Docker Compose.
- It includes all relevant commands, services, and troubleshooting tips.
- Customization and resetting instructions are also included for flexibility in the development process.








