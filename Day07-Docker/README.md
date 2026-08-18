# Day 07 - Docker Advanced Concepts

**Date:** 17-18 August 2026  
**Track:** DevOps

## Objective

Day 07 mein Docker ke advanced concepts ko understand aur hands-on practice kiya.

## Topics Covered

- Dockerfile
- Docker Image Management
- Custom Docker Images
- Multi-Stage Dockerfile
- Docker Networking
- Docker Volumes
- Data Persistence
- Docker Compose
- Private Registry Basics
- CI/CD Integration Concepts

## 1. Dockerfile

Dockerfile ek text file hai jisme Docker image build karne ke instructions hote hain.

Example:

```dockerfile
FROM nginx:latest

COPY index.html /usr/share/nginx/html/

EXPOSE 80

Docker Image Management
docker images
docker pull nginx
docker build -t my-nginx .
docker rmi nginx
docker image inspect nginx

3. Custom Docker Image

Hands-on:

Dockerfile create kiya
index.html create kiya
Custom image build ki
Container run kiya
docker build -t my-nginx .
docker run -d --name my-nginx -p 8080:80 my-nginx

4. Multi-Stage Dockerfile

Multi-stage builds ka use final Docker image ka size reduce karne ke liye kiya jata hai.

FROM node:latest AS build


WORKDIR /app
COPY . .
RUN npm install && npm run build


FROM nginx:latest
COPY --from=build /app/build /usr/share/nginx/html/
EXPOSE 80

5. Docker Networking

Docker containers ko ek dusre ke saath communicate karne ke liye networks use hote hain.

docker network ls
docker network create my-network
docker run -d --name nginx1 --network my-network nginx
docker network inspect my-network
6. Docker Volumes & Persistence

Volumes ka use container delete hone ke baad bhi data ko persist karne ke liye hota hai.

docker volume create my-volume
docker volume ls
docker run -d -v my-volume:/data nginx
7. Docker Compose

Docker Compose ka use multiple containers/services ko ek saath manage karne ke liye hota hai.

Basic commands:

docker compose up -d
docker compose ps
docker compose logs
docker compose down
8. Private Registry

Private registry ka use Docker images ko privately store aur manage karne ke liye kiya jata hai.

Concepts covered:

Registry
Image tagging
Image push/pull
Private image storage
9. CI/CD Integration

Docker ko CI/CD pipelines ke saath integrate kiya ja sakta hai.

Basic flow:

Code
  ↓
Build Docker Image
  ↓
Test
  ↓
Push Image to Registry
  ↓
Deploy Container
Hands-on Practice
Created Dockerfile
Built custom Docker image
Ran custom container
Practiced multi-stage builds
Created Docker networks
Worked with Docker volumes
Practiced Docker Compose
Understood private registry concepts
Understood Docker CI/CD workflow
Key Takeaways
Dockerfile se custom images create karna
Images ko build, tag aur manage karna
Multi-stage builds se image size optimize karna
Container networking samajhna
Volumes se persistent data maintain karna
Docker Compose se multi-container applications manage karna
Docker ko CI/CD pipeline mein integrate karna
