# WordPress with Docker Compose

This setup runs WordPress with Nginx and MySQL using Docker Compose.

## Services

- **MySQL 8.0**: Database server
- **WordPress 5.1.1 (FPM Alpine)**: WordPress application with PHP-FPM

## Getting Started

### Prerequisites

- Docker installed
- Docker Compose installed

### Starting the Services

```bash
docker-compose up -d
```

### Checking Service Status

```bash
docker-compose ps
```

### Accessing WordPress

Open your browser and navigate to:

```
http://localhost
```

Follow the WordPress installation wizard to complete setup.

### Stopping the Services

```bash
docker-compose stop
```

### Removing Everything (including volumes)

```bash
docker-compose down -v
```

## Configuration

## Volumes

- `./wordpress-data`: Contains WordPress files
- `./mysql-data`: Contains MySQL database files

## Network

All services communicate on the `app-network` bridge network.

## Logs

View logs for specific services:

```bash
docker-compose logs db
docker-compose logs wordpress
docker-compose logs webserver
```

View all logs:

```bash
docker-compose logs
```

Follow logs in real-time:

```bash
docker-compose logs -f
```

## Troubleshooting

If you encounter issues:

1. Check container status: `docker-compose ps`
2. View logs: `docker-compose logs`
3. Restart services: `docker-compose restart`
4. Rebuild containers: `docker-compose up -d --force-recreate`
