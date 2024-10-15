# 🚀 Nextcloud with Traefik on Docker

![Nextcloud Logo](https://cdn.icon-icons.com/icons2/2699/PNG/512/nextcloud_logo_icon_168082.png) 
![Traefik Logo](https://raw.githubusercontent.com/docker-library/docs/a6cc2c5f4bc6658168f2a0abbb0307acaefff80e/traefik/logo.png)

This project provides a Docker Compose configuration for setting up Nextcloud with Traefik as a reverse proxy, MariaDB as the database, and Redis for caching. It's designed to be flexible for both local development and production deployment.

## 🌟 Features

- 🐳 Fully dockerized setup
- 🔒 HTTPS support with automatic certificate management (for production)
- 🔄 Traefik as reverse proxy and load balancer
- 📊 MariaDB for database
- ⚡ Redis for caching
- 🔧 Easy configuration via environment variables
- 🔀 Profile-based setup for local development and production environments

## 🛠️ Requirements

- [Docker](https://docs.docker.com/get-docker/) (v20.10 or higher)
- [Docker Compose](https://docs.docker.com/compose/install/) (v1.27 or higher)

## 🚀 Getting Started

### Clone the Repository

```bash
git clone https://github.com/c0lap5o/nextcloud
cd nextcloud
```

## Create a .env File

 Create a .env file in the project root directory example:

```text
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

# Deployment mode (set to "production" for HTTPS, "local" for HTTP)
DEPLOYMENT_MODE=local
```

# Running the Project

### Local Development

To start the services for local development, run:

```bash
docker-compose --profile local up -d
```
Access Nextcloud at http://nextcloud.localhost

### Production Environment

To start the services for production, run:

```bash
docker-compose --profile production up -d
```
Access Nextcloud at https://yourdomain.com. Replace yourdomain.com with your actual domain.

### Stopping the Services

To stop all running services, use:
```bash
docker-compose down
```

## 🔧 Configuration

### Traefik Dashboard

The Traefik dashboard is available at http://localhost:8080 in local mode. It is disabled in production for security reasons.

## Customizing Nextcloud
Customize your Nextcloud installation by modifying the configuration files in the ./config directory. Data is stored in the ./data directory.

## 📁 Project Structure

```text
.
├── docker-compose.yml
├── .env
├── app/
├── config/
├── data/
├── db/
└── letsencrypt/
```

## 🔐 Security Notes

Never use the provided example passwords in production.
Always use strong, unique passwords for all services in a production environment.
Keep your .env file secure and never commit it to version control.

## 🆘 Troubleshooting

If you can't access Nextcloud, check your Docker logs:

```bash
docker-compose logs traefik
docker-compose logs nextcloud-app
```

Ensure that your browser cache is cleared if you experience unexpected HTTPS redirection.
For SSL issues, verify that your domain is pointing to your server's IP address.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request or open an issue for suggestions or improvements.

## 📄 License

This project is open source and available under the [MIT License](https://opensource.org/license/MIT).

## 🙏 Acknowledgments

Nextcloud\
Traefik\
Docker\
MariaDB\
Redis
