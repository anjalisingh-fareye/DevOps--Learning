 #Two-Tier Docker Application

A simple two-tier application deployed using Docker and Docker Compose.

Project Overview

This project demonstrates how to containerize an application, build a custom Docker image, run services with Docker Compose, and troubleshoot container networking/DNS issues.

Architecture

                Client / Browser
                       |
                       v
                +--------------+
                |  App Container|
                | Node.js       |
                | Port 3000     |
                +--------------+
                       |
                       v
                +--------------+
                | Database      |
                | Container     |
                +--------------+

#Technologies Used

Docker

Docker Compose

Node.js 22 Alpine

npm

Docker Networking

Linux / Ubuntu

Git & GitHub

Project Structure

two-tier-app/
├── app/
│   ├── Dockerfile
│   ├── package.json
│   ├── package-lock.json
│   └── ...application files
└── docker-compose.yml

Dockerfile

Example Dockerfile used for the application:

FROM node:22-alpine

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 3000

CMD ["npm", "start"]

Dockerfile Instructions

Instruction

Purpose

FROM

Selects the base image

WORKDIR

Sets the working directory inside the container

COPY

Copies application files into the image

RUN

Executes commands while building the image

EXPOSE

Documents the application port

CMD

Defines the default command when the container starts

Docker Compose

A basic Compose configuration can look like:

services:
  app:
    build:
      context: ./app
      network: host
    ports:
      - "3000:3000"

network: host is useful as a workaround when Docker's default build network cannot resolve external DNS names. For normal deployments, use the networking mode required by the environment rather than enabling host networking without a reason.

Build the Application Image

From the project root:

cd ~/two-tier-app

Build using the app directory as the Docker build context:

docker build -t two-tier-app ./app

If Docker's default build network has DNS problems:

docker build --network=host -t two-tier-app ./app

Run the Container

docker run -d --name two-tier-app -p 3000:3000 two-tier-app

Check the running container:

docker ps

View logs:

docker logs two-tier-app

Stop the container:

docker stop two-tier-app

Remove the container:

docker rm two-tier-app

Docker Compose Commands

Build the services:

docker compose build

Start the application:

docker compose up -d

Check services:

docker compose ps

View logs:

docker compose logs -f

Stop the application:

docker compose down

Networking Troubleshooting

Problem

During image build, npm returned:

npm error code EAI_AGAIN
npm error syscall getaddrinfo
npm error request to https://registry.npmjs.org/express failed

Meaning

EAI_AGAIN indicates a temporary DNS/name-resolution failure. In this setup, the host could resolve registry.npmjs.org, while the normal Docker bridge/build network could not.

Verify Host DNS

ping -c 3 registry.npmjs.org

resolvectl status

Test DNS Inside a Container

docker run --rm node:22-alpine getent hosts registry.npmjs.org

If no address is returned, test through the host network:

docker run --rm --network=host node:22-alpine getent hosts registry.npmjs.org

If the host-network test works, the issue is related to Docker's default/bridge networking or DNS path.

Build Using Host Networking

docker build --network=host -t two-tier-app ./app

Important Fix: Dockerfile Location

The Dockerfile is inside the app/ directory, not the project root.

Correct:

docker build -t two-tier-app ./app

Incorrect from the project root:

docker build -t two-tier-app .

The second command expects this file:

~/two-tier-app/Dockerfile

which does not exist in this project structure.

Useful Docker Commands

List images:

docker images

List running containers:

docker ps

List all containers:

docker ps -a

Inspect an image:

docker inspect two-tier-app

Enter a running container:

docker exec -it two-tier-app sh

View Docker networks:

docker network ls

Inspect the bridge network:

docker network inspect bridge

Learning Outcomes

Understood Docker images and containers.

Created a custom Dockerfile.

Built a Node.js image from node:22-alpine.

Used Docker Compose to manage application services.

Learned how Docker build context works.

Practiced port mapping and container management.

Troubleshot DNS/network connectivity during npm install.

Understood the difference between Docker bridge networking and host networking.

Common Errors

Dockerfile not found

lstat .../two-tier-app/Dockerfile: no such file or directory

Fix:

docker build -t two-tier-app ./app

npm EAI_AGAIN

getaddrinfo EAI_AGAIN registry.npmjs.org

First test:

docker run --rm --network=host node:22-alpine getent hosts registry.npmjs.org

If this works, investigate Docker bridge/build DNS configuration or use host networking as an environment-approved workaround.

Buildx warning

You may see:

Docker Compose is configured to build using Bake, but buildx isn't installed

This is a warning about the build tooling and is separate from the npm EAI_AGAIN DNS error.

Git Commands

Initialize repository if needed:

git init

Check status:

git status

Add files:

git add .

Commit:

git commit -m "Add two-tier Docker application"

Add remote repository:

git remote add origin <YOUR_GITHUB_REPOSITORY_URL>

Push:

git branch -M main
git push -u origin main

