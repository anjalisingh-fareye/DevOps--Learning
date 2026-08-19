# Day 09- Docker (All about)

## Objective

Understand the basics of Docker and Containers, VM vs Container, Docker Architecture, and important Docker Components.

---

## 1. Introduction to Docker

Docker is an open-source platform used to **build, package, ship, and run applications inside containers**.

Docker packages an application along with its required libraries, dependencies, and configuration into a **Docker Image**. This image can be used to run the application consistently across different environments.

### Benefits of Docker

- Lightweight
- Portable
- Fast startup
- Consistent environment
- Application isolation
- Efficient resource utilization

---

## 2. What is a Container?

A **Container is a running instance of a Docker Image**.

A container provides an isolated environment where an application and its dependencies can run.

### Example

VM = Guest OS + Application

Container = Application + Dependencies

```bash

Docker Client
      |
      | REST API
      ↓
Docker Daemon
      |
      ├── Images
      ├── Containers
      ├── Networks
      └── Volumes
      |
      ↓
Docker Registry
docker pull nginx
docker run -d --name my-nginx nginx
docker ps

docker build
docker pull
docker run
docker ps

# Check Docker version
docker --version

# Download an image
docker pull nginx

# List images
docker images

# Run a container
docker run -d --name my-nginx nginx

# List running containers
docker ps

# List all containers
docker ps -a

# Stop a container
docker stop my-nginx

# Remove a container
docker rm my-nginx
