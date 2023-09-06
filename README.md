Odoo Docker
===========

This project sets up an Odoo instance using Docker Compose with a PostgreSQL database as the backend.

Prerequisites
-------------

Before getting started, make sure you have the following software installed on your system:

*   Docker: [Install Docker](https://docs.docker.com/get-docker/)
*   Docker Compose: [Install Docker Compose](https://docs.docker.com/compose/install/)

Usage
-----

1.  Clone this repository to your local machine:
```
git clone https://github.com/jbarreraballestas/odoo_docker.git
cd odoo_docker
```
    
    

3.  Create a `.env` file in the project root directory with the following content:

```
# PostgreSQL environment variables
POSTGRES_DB=postgres
POSTGRES_PASSWORD=your-secret-password
POSTGRES_USER=odoo
PGDATA=/var/lib/postgresql/data/pgdata

# Odoo environment variables
HOST=postgres
USER=odoo
PASSWORD=your-secret-password
```

    

To generate and replace `your-secret-password` with a secure password, you can use the following command:

```
openssl rand -base64 30

```
    
    

7.  Run Odoo and PostgreSQL containers using Docker Compose:

```
docker-compose up -d

```
    
    

9.  Access Odoo in your web browser at [http://localhost:80](http://localhost:80).

Customization
-------------

*   You can customize the PostgreSQL and Odoo configuration in the `.env` file.
*   Odoo data will be stored in the `odoo_data` volume, and PostgreSQL data will be stored in the `postgres_data` volume. You can backup and restore data by managing these volumes.

Stopping the Containers
-----------------------

To stop the containers, run the following command in the project directory:

```
docker-compose down

```

    

This will stop and remove the containers but preserve the data volumes.

License
-------

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
