# Nextcloud with Traefik on Docker

![Nextcloud Logo](https://nextcloud.com/wp-content/uploads/2020/10/nextcloud-logo.svg)

## Overview

This project sets up **Nextcloud**, a powerful open-source file sync and share solution, behind **Traefik**, a modern reverse proxy and load balancer, using Docker Compose. The configuration supports both local development and production environments with automatic HTTP to HTTPS redirection in production.

## Features

- **Nextcloud**: Self-hosted file sharing and collaboration platform.
- **Traefik**: Dynamic reverse proxy with automatic HTTPS using Let's Encrypt.
- **Docker Compose**: Easy setup and management of services.
- **Profiles**: Switch between local development and production environments effortlessly.

## Requirements

- [Docker](https://docs.docker.com/get-docker/) (v20.10 or higher)
- [Docker Compose](https://docs.docker.com/compose/install/) (v1.27 or higher)

## Getting Started

### Clone the Repository

```bash
git clone https://github.com/yourusername/nextcloud-traefik-docker.git
cd nextcloud-traefik-docker
```

### Create a '.env' FIle

### Create a .env file in the project root directory with the following content:

```bash
# MySQL/MariaDB settings
MYSQL_ROOT_PASSWORD=rootpassword123
MYSQL_PASSWORD=nextclouddbpass123
NEXTCLOUD_DB=nextcloud_db
NEXTCLOUD_DB_USER=nextcloud_user

# Redis settings
REDIS_PASSWORD=redispassword123

# Nextcloud settings
NEXTCLOUD_HOST=nextcloud.localhost

# Let's Encrypt settings (for production)
ACME_EMAIL=your.email@example.com
```

## Running the Project

### Local Development

#### To start the services for local development, run:

```bash
docker-compose --profile local up -d
```
You can access Nextcloud at http://nextcloud.localhost.


##  Production Environment

###  To start the services for production, run:

```bash
docker-compose --profile production up -d
```

You can access Nextcloud at https://yourdomain.com. Make sure to replace yourdomain.com with your actual domain.

## Stopping the Services

### To stop all running services, use:

```bash
docker-compose down
```

## Configuration

### Traefik Dashboard

The Traefik dashboard is available at http://localhost:8080 in local mode. It is disabled in production for security reasons.

## Customizing Nextcloud

You can customize your Nextcloud installation by modifying the configuration files located in the ./config directory. The data will be stored in the ./data directory.

## Troubleshooting

If you encounter issues accessing Nextcloud, check your Docker logs:

```bash
docker-compose logs traefik
docker-compose logs nextcloud-app
```

Ensure that your browser cache is cleared if you experience unexpected HTTPS redirection.

## Contributing

Contributions are welcome! Please feel free to submit a pull request or open an issue if you have suggestions or improvements.

## License
 
This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

Nextcloud
Traefik
Docker

