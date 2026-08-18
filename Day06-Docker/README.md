## Objective

The objective of Day 06 was to understand Docker fundamentals, containers,
Docker architecture, Docker components, Docker images, Docker Engine,
Docker Client, Docker Registry, and basic Docker commands.

---

# 1. Introduction to Docker

Docker is an open-source containerization platform used to build, package,
ship, and run applications in lightweight and isolated containers.

Docker packages an application along with its dependencies so that it can
run consistently across different environments.

### Docker Flow

```text
Application
     +
Dependencies
     ↓
Docker Image
     ↓
Docker Container
     ↓
Running Application

# Day 6 Hands-on Practice

## Task 1: Pull Nginx Image

docker pull nginx

### Expected Result

Nginx image should be downloaded successfully.

---

## Task 2: Run Nginx Container

docker run -d --name my-nginx -p 8080:80 nginx

### Verify

docker ps

### Expected Result

my-nginx should be in Running status.

---

## Task 3: Enter Container

docker exec -it my-nginx bash

### Verify

hostname
ls
pwd

### Expected Result

Commands should execute inside the container.

---

## Task 4: Stop Container

docker stop my-nginx

### Verify

docker ps

### Expected Result

my-nginx should not appear in running containers.

---

## Task 5: Start Container Again

docker start my-nginx

### Verify

docker ps

### Expected Result

my-nginx should be running again.

---

## Task 6: Remove Container

docker stop my-nginx
docker rm my-nginx

### Verify

docker ps -a

### Expected Result

my-nginx should be removed.
