# README for Docker Compose Setup

This Docker Compose file creates two services, a MySQL database and a Keycloak server.

## Prerequisites
- Docker Compose should be installed on the host machine.

## Setup
1. Clone the repository or download the Docker Compose file.
2. Navigate to the directory containing the Docker Compose file.
3. Run `docker-compose up -d` to start the containers in detached mode.
4. Wait for a few minutes for the services to start up completely.
5. The MySQL service is exposed on port `3306` and the Keycloak service is exposed on port `8080`.

## Service Details
- **MySQL**: The MySQL service uses version 8.0.32 of the official MySQL Docker image. It creates a volume to persist the data in the `./mysql` directory relative to the Docker Compose file. The root password is set to `root`, and a database named `keycloak` is created with a user `keycloak` and password `password`.
- **Keycloak**: The Keycloak service uses version 21.0.2 of the official Keycloak Docker image from Quay.io. It sets the database to use MySQL, and the address of the MySQL service is set to `mysql`. The database name, username, and password are the same as those set up in the MySQL service. The admin user is set to `admin` with password `admin`.

## Additional Notes
- To stop the services, run `docker-compose down` in the same directory as the Docker Compose file.
- If you want to access the logs of the containers, run `docker-compose logs <service_name>` where `<service_name>` is either `mysql` or `keycloak`.
