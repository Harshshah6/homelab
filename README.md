# Self-Hosted Services

A collection of Docker Compose configurations for various self-hosted applications and services.

## Services Overview

### Infrastructure & Networking
- **[Traefik](traefik-self-hosted/)** - Modern reverse proxy and load balancer
- **[Nginx Proxy Manager](nginx-proxy-manager/)** - User-friendly nginx reverse proxy
- **[Cloudflared Tunnel](cloudflared-tunnel/)** - Secure tunnel for exposing services

### DNS & Security
- **[Pi-hole](pihole-selfhosted/)** - Network-wide ad blocking and DNS
- **[AdGuard Home](adguard-home/)** - DNS-level privacy protection

### Storage & File Management
- **[Garage](garage-self-hosted/)** - Lightweight S3-compatible distributed storage
- **[File Browser](filebrowser-selfhosted/)** - Simple web-based file manager

### Container Management
- **[Portainer](portainer-selfhosted/)** - Docker container management UI
- **[Komodo](komodo-selfhosted/)** - Portainer alternative for container management

### Monitoring & Analytics
- **[Tianji](tianji-selfhosted/)** - Uptime monitoring and status page
- **[Termix](termix-selfhosted/)** - SSH access, files, monitoring, and Docker control

### Gaming
- **[Minecraft](minecraft-selfhosted/)** - Self-hosted Minecraft server

### Development & Tools
- **[GitLab](gitlab-selfhosted/)** - Self-hosted Git repository and CI/CD
- **[Oak](oak-selhosted/)** - Homepage for self-hosted services
- **[Notifuse](notifuse-selfhosted/)** - Email notification platform

## Quick Start

Each service has its own directory with a `docker-compose.yml` file. To start a service:

```sh
cd <service-directory>
docker-compose up -d
```

## Environment Configuration

Some services use `.env` files for configuration:

- Copy `.env.example` to `.env` if provided
- Update variables with your specific configuration
- **Do not commit `.env` files** (they're in `.gitignore`)

Example:
```sh
cd cloudflared-tunnel
cp .env.example .env
# Edit .env with your settings
docker-compose up -d
```

## Project Structure

```
.
├── adguard-home/              # DNS privacy protection
├── cloudflared-tunnel/        # Tunnel configuration with .env
├── filebrowser-selfhosted/    # File browser service
├── garage-self-hosted/        # S3-compatible storage
├── gitlab-selfhosted/         # Git repository & CI/CD
├── komodo-selfhosted/         # Portainer Alternative
├── minecraft-selfhosted/      # Minecraft server
├── nginx-proxy-manager/       # Reverse proxy
├── notifuse-selfhosted/       # Emailing platform
├── oak-selhosted/             # Homepage for self-hosted services.
├── pihole-selfhosted/         # Network ad blocking
├── portainer-selfhosted/      # Container management
├── termix-selfhosted/         # SSH access, files, monitoring, and Docker control
├── tianji-selfhosted/         # Uptime monitoring
└── traefik-self-hosted/       # Advanced reverse proxy
```

## Common Operations

### View service logs
```sh
docker-compose logs -f <service-name>
```

### Stop a service
```sh
docker-compose down
```

### Remove data (warning: destructive)
```sh
docker-compose down -v
```

## Prerequisites

- Docker & Docker Compose installed
- Appropriate ports available on your host
- Sufficient disk space for each service

## Security Notes

- Keep `.env` files with sensitive data secure
- Review firewall rules before exposing services
- Use strong passwords for all applications
- Consider using reverse proxies (Traefik/Nginx) for external access
- Enable authentication where available

## Support & Documentation

Refer to individual service directories for specific configuration and setup instructions.

## License

See individual service documentation for licensing information.