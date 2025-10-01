# MySQL Docker Setup

This Docker Compose configuration sets up a MySQL 8.0 database server.

## Configuration

- **Image**: mysql:8.0
- **Container Name**: mysql-db
- **Port**: 3306 (mapped to host port 3306)
- **Root Password**: rootpassword
- **Database**: testdb
- **User**: user
- **Password**: userpassword

## Usage

### Start the MySQL container:

```bash
docker-compose up -d
```

### Stop the MySQL container:

```bash
docker-compose down
```

### Connect to MySQL:

```bash
# Using docker exec
docker exec -it mysql-db mysql -u root -p

# Using mysql client (if installed locally)
mysql -h localhost -P 3306 -u root -p
mysql -h localhost -P 3306 -u user -p
```

## Data Persistence

Data is persisted in a Docker volume named `mysql_data`. This ensures your data survives container restarts and removals.

## Initialization Scripts

You can place SQL scripts in the `./init` directory, and they will be executed when the container is first created. These scripts can be used to:

- Create additional databases
- Create tables
- Insert initial data
- Set up users and permissions

## Environment Variables

You can modify the following environment variables in the docker-compose.yml file:

- `MYSQL_ROOT_PASSWORD`: Password for the root user
- `MYSQL_DATABASE`: Name of the database to create
- `MYSQL_USER`: Name of a user to create
- `MYSQL_PASSWORD`: Password for the created user

## Security Notes

- Change the default passwords before using in production
- Consider using Docker secrets for sensitive data in production environments
- Restrict network access as needed
