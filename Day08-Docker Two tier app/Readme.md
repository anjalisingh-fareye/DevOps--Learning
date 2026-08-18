#**Day 09 – Two-Tier Docker Application Deployment on AWS EC2**

Date: 18 August 2026
Track: DevOps
Topic: Building Multi-Tier Project using Docker & Deploying on AWS EC2

#**Two-Tier Docker Application**

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

Technologies Used

Docker

Docker Compose

Node.js 22 Alpine

npm

Docker Networking

Linux / Ubuntu

Git & GitHub

Objective

Build and deploy a Two-Tier Application using Docker Compose.

The project contains:

Application Tier: Node.js + Express
Database Tier: MySQL
Docker Networking
Docker Volume
Docker Compose
AWS EC2 deployment
Architecture
                 Internet / Browser
                        |
                        | Port 3000
                        ↓
                ┌─────────────────┐
                │   Node.js App   │
                │   Express       │
                │   Docker        │
                └────────┬────────┘
                         |
                         | db:3306
                         ↓
                ┌─────────────────┐
                │     MySQL       │
                │     Docker      │
                └────────┬────────┘
                         |
                         ↓
                  Docker Volume
                   mysql-data
                         
                AWS EC2 Instance
1. Project Structure
two-tier-app/
├── app/
│   ├── Dockerfile
│   ├── package.json
│   └── server.js
├── docs/
│   ├── commands.md
│   └── troubleshooting.md
├── docker-compose.yml
├── .gitignore
└── README.md
2. Application Tier

Created a Node.js application using:

Express.js
MySQL2

Application runs on:

Port: 3000

Test endpoint:

/

Response:

Two-Tier Docker Application is Running!
3. Database Tier

Used:

MySQL 8

Database:

appdb

Application connects to MySQL using the Docker service name:

db:3306
4. Dockerfile

Created Dockerfile for Node.js application:

FROM node:22-alpine


WORKDIR /app


COPY package.json .


RUN npm install


COPY server.js .


EXPOSE 3000


CMD ["npm", "start"]
5. Docker Compose

Docker Compose was used to run both services:

app
db

The services communicate through the Docker Compose network.

Database persistence was implemented using:

mysql-data

Docker volume.

6. Docker Network

Docker Compose automatically created:

two-tier-app_default

The application accesses MySQL using:

db

instead of a hard-coded container IP.

7. Troubleshooting

During the build, encountered:

npm error code EAI_AGAIN
Cause

Temporary DNS/network resolution issue while the Docker build was trying to reach:

registry.npmjs.org

Tested connectivity using:

curl -I https://registry.npmjs.org

and:

docker run --rm node:22-alpine getent hosts registry.npmjs.org

Also tested host networking:

docker run --rm --network host node:22-alpine npm view express version

After resolving the Docker networking issue, the image built successfully.

8. MySQL Connection Issue

Initially received:

ECONNREFUSED
Cause

MySQL container was running, but MySQL itself was still initializing.

Added retry logic in server.js:

function connectDB() {
    db.connect((err) => {
        if (err) {
            console.log("MySQL not ready, retrying in 5 seconds...");
            setTimeout(connectDB, 5000);
            return;
        }


        console.log("Connected to MySQL!");
    });
}

After rebuilding:

docker compose build --no-cache
docker compose up -d

the application successfully connected to MySQL.

9. Local Testing

Checked containers:

docker compose ps

Result:

two-tier-app-app-1    Up    0.0.0.0:3000->3000/tcp
two-tier-app-db-1     Up

Application test:

http://localhost:3000

Output:

Two-Tier Docker Application is Running!

Database test:

http://localhost:3000/db

Output:

Database Connected! Time: ...
10. AWS EC2 Deployment

The next phase is deploying the same application on an AWS EC2 Ubuntu instance.

Deployment flow
GitHub
   |
   ↓
AWS EC2
   |
   ↓
Docker
   |
   ↓
Docker Compose
   |
   ├── Node.js Container
   |
   └── MySQL Container
EC2 tasks
Create Ubuntu EC2 instance
Configure Security Group
Connect through SSH
Install Docker
Install Docker Compose
Clone GitHub repository
Build Docker images
Start containers
Test application using EC2 public IP
11. EC2 Security Group

Required ports:

Port	Purpose
22	SSH
3000	Node.js application

MySQL port 3306 should not be exposed publicly.

MySQL remains accessible only inside the Docker network.

12. Important Docker Commands
docker compose build
docker compose build --no-cache
docker compose up -d
docker compose down
docker compose ps
docker compose logs
docker compose logs -f
docker ps
docker images
docker network ls
docker volume ls
13. Learning Outcomes

By the end of Day 09, I practiced:

Building a two-tier application
Creating a Dockerfile
Building custom Docker images
Running multiple containers
Docker Compose
Docker networking
Container-to-container communication
Docker volumes
MySQL persistence
Node.js + MySQL integration
Troubleshooting Docker DNS
Troubleshooting database startup issues
Preparing application for AWS EC2 deployment
GitHub-based deployment workflow 

