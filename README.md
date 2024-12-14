# Docker Commands Cheat Sheet

This repository contains a comprehensive guide to Docker commands and their usage, including flowcharts and detailed explanations.

## Table of Contents
- [Basic Commands](#basic-commands)
- [Container Management](#container-management)
- [Image Management](#image-management)
- [Network Management](#network-management)
- [Volume Management](#volume-management)
- [Docker Compose](#docker-compose)

## Basic Commands

### Container Lifecycle
```bash
# Run a container
docker run [OPTIONS] IMAGE [COMMAND]
  -d          # Run in detached mode
  -p          # Port mapping (host:container)
  -v          # Volume mounting
  --name      # Assign container name
  -e          # Set environment variables
  --network   # Connect to network
  --rm        # Remove when stopped
```

### Container Management
```bash
# List containers
docker ps [OPTIONS]
  -a          # Show all containers
  -q          # Only show IDs

# Container operations
docker start CONTAINER
docker stop CONTAINER
docker restart CONTAINER
docker rm [-f] CONTAINER
```

## Image Management

```bash
# Image operations
docker images                  # List images
docker pull IMAGE[:TAG]       # Download image
docker push IMAGE[:TAG]       # Upload image
docker rmi IMAGE              # Remove image
docker build [OPTIONS] PATH   # Build image
  -t          # Tag the image
  --no-cache  # Build without cache
```

## Network Management

```bash
docker network create NETWORK
docker network ls
docker network rm NETWORK
docker network connect NETWORK CONTAINER
docker network disconnect NETWORK CONTAINER
```

## Volume Management

```bash
docker volume create VOLUME
docker volume ls
docker volume rm VOLUME
docker volume inspect VOLUME
```

## Docker Compose

```bash
docker-compose up [-d]        # Create and start containers
docker-compose down          # Stop and remove containers
docker-compose ps           # List containers
docker-compose logs         # View logs
docker-compose build       # Build/rebuild services
```

## Common Use Cases

1. Running a Web Application
```bash
docker run -d -p 80:80 --name myapp nginx
```

2. Building a Custom Image
```bash
docker build -t myapp:1.0 .
```

3. Managing Persistent Data
```bash
docker volume create mydata
docker run -v mydata:/data myapp
```

4. Creating a Custom Network
```bash
docker network create mynetwork
docker run --network mynetwork myapp
```

## Flowchart
The repository includes a detailed flowchart showing the relationships between different Docker commands. You can find it in the `flowchart.md` file.