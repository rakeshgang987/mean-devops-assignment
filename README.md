In this DevOps task, you need to build and deploy a full-stack CRUD application using the MEAN stack (MongoDB, Express, Angular 15, and Node.js). The backend will be developed with Node.js and Express to provide REST APIs, connecting to a MongoDB database. The frontend will be an Angular application utilizing HTTPClient for communication.  

The application will manage a collection of tutorials, where each tutorial includes an ID, title, description, and published status. Users will be able to create, retrieve, update, and delete tutorials. Additionally, a search box will allow users to find tutorials by title.

## Project setup

### Node.js Server

cd backend

npm install

You can update the MongoDB credentials by modifying the `db.config.js` file located in `app/config/`.

Run `node server.js`

### Angular Client

cd frontend

npm install

Run `ng serve --port 8081`

You can modify the `src/app/services/tutorial.service.ts` file to adjust how the frontend interacts with the backend.

Navigate to `http://localhost:8081/`
📌 Project Overview

This project demonstrates the complete DevOps lifecycle of a full-stack CRUD application built using the MEAN stack:

MongoDB

Express

Angular 15

Node.js

The goal of this assignment was to:

Containerize frontend and backend applications

Deploy them on a cloud-based Ubuntu VM

Configure MongoDB

Implement CI/CD pipeline automation

Configure Nginx reverse proxy

Ensure the application is accessible via port 80

🏗️ Application Architecture

'User (Browser)
        ↓
Nginx (Port 80)
        ↓
Angular Frontend
        ↓
Node.js + Express Backend
        ↓
MongoDB Database

The entire application is accessible via:

http://YOUR_EC2_PUBLIC_IP
🛠️ Technology Stack

Angular 15

Node.js

Express.js

MongoDB

Docker

Docker Compose

GitHub Actions (CI/CD)

AWS EC2 (Ubuntu)

Nginx Reverse Proxy

📂 Repository Structure
.
├── backend/
│   └── Dockerfile
│
├── frontend/
│   └── Dockerfile
│
├── docker-compose.yml
├── .github/workflows/deploy.yml
├── nginx.conf (if applicable)
└── README.md
🐳 Containerization
🔹 Backend Dockerfile

Uses Node.js base image

Installs dependencies

Exposes backend port

Runs Express server

🔹 Frontend Dockerfile

Multi-stage build

Builds Angular production files

Uses Nginx to serve static files

Exposes port 80

🔹 Database

MongoDB is deployed using the official MongoDB Docker image within Docker Compose.

☁️ Cloud Infrastructure Setup (AWS EC2)

Ubuntu Server (EC2 Instance)

Docker & Docker Compose installed

Security Group configured:

Port 22 (SSH)

Port 80 (HTTP)

The application is deployed using Docker Compose on the EC2 instance.

🚀 Deployment Using Docker Compose

On the EC2 instance:

docker compose up -d

To verify running containers:

docker ps

Application accessible at:

http://YOUR_EC2_PUBLIC_IP
🔁 CI/CD Pipeline (GitHub Actions)

CI/CD is implemented using GitHub Actions.

Workflow Process:

Triggered on push to main branch

Builds updated Docker images for frontend and backend

Pushes images to Docker Hub

SSH into EC2 server

Pulls latest images

Restarts containers using Docker Compose

Docker Hub Images:

YOUR_DOCKERHUB_USERNAME/dd-mean-frontend

YOUR_DOCKERHUB_USERNAME/dd-mean-backend

🌐 Nginx Reverse Proxy

Nginx serves the Angular frontend

Proxies API requests internally to backend

Entire application accessible via port 80

No need to expose backend port publicly

##### Screenshots Included

The repository includes screenshots demonstrating:

* GitHub Actions CI/CD pipeline execution

* Docker image build and push process (Docker Hub)

* EC2 deployment (docker ps output)

* Working application UI in browser

* Docker Compose configuration

* Nginx setup details

Screenshots are available in:

/screenshots/
🔐 GitHub Secrets Configured

DOCKER_USERNAME

DOCKER_PASSWORD

EC2_HOST

EC2_KEY

Sensitive credentials are securely stored in GitHub Secrets and not exposed in the repository.

############# Assignment Requirements Completed

* Created new GitHub repository
* Pushed complete project code
* Created Dockerfiles for frontend and backend
* Built and pushed images to Docker Hub
* Set up Ubuntu VM on AWS EC2
* Used Docker Compose for deployment
*Used official MongoDB Docker image
*Implemented CI/CD pipeline using GitHub Actions
* Automated image build, push, and deployment
* Configured Nginx reverse proxy
* Application accessible via port 80
* Detailed documentation and screenshots provided

🔒 Infrastructure Status

The cloud infrastructure has not been deleted.

The EC2 instance may be stopped to save cost but can be restarted for live demonstration in the next round.

🔗 Submission Details

GitHub Repository URL:

YOUR_GITHUB_REPO_URL

Live Application:

http://YOUR_EC2_PUBLIC_IP'
