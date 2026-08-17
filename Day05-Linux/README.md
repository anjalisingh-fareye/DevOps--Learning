 Day 5 – Understanding of Docker

## What is Docker?

Docker is a containerization platform used to build, package, and run applications in isolated containers.

## Key Concepts

- Docker Image – Template used to create containers.
- Docker Container – Running instance of an image.
- Dockerfile – Instructions used to build a Docker image.
- Docker Engine – Runs and manages Docker containers.
- Docker Registry – Stores and distributes Docker images.
- Docker Hub – Public registry for Docker images.
- Docker Volume – Used for persistent data.
- Docker Network – Enables communication between containers.

## Basic Understanding

Understood how Docker works, why containers are used, and the difference between Docker images and containers.

## Docker Installation

### Check Ubuntu Version

cat /etc/os-release

### Update Packages

sudo apt update

### Install Docker

sudo apt install docker.io -y

### Start Docker

sudo systemctl start docker

### Enable Docker

sudo systemctl enable docker

### Check Docker Version

docker --version

### Check Docker Service

sudo systemctl status docker

### Test Docker

sudo docker run hello-world

## Hands-on
- Installed Docker on Ubuntu.
- Started and enabled Docker service.
- Verified Docker installation.
- Ran the `hello-world` test container.
