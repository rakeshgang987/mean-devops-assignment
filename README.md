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
####################################

📌 Project Overview

This project demonstrates the complete DevOps lifecycle of a full-stack CRUD application built using the MEAN stack:

MongoDB

Express

Angular 15

Node.js

🎯 Assignment Objectives

Containerize frontend and backend applications

Deploy on a cloud-based Ubuntu VM (AWS EC2)

Configure MongoDB

Implement CI/CD pipeline automation

Configure Nginx reverse proxy

Ensure application accessibility via Port 80

## Application Architecture

```
User (Browser)
        ↓
Nginx (Port 80)
        ↓
Angular Frontend
        ↓
Node.js + Express Backend
        ↓
MongoDB Database
```
🌐 Live Application:

    ``` http://YOUR_EC2_PUBLIC_IP ```

🛠️ Technology Stack
 ```
| Layer            | Technology        |
| ---------------- | ----------------- |
| Frontend         | Angular 15        |
| Backend          | Node.js + Express |
| Database         | MongoDB           |
| Containerization | Docker            |
| Orchestration    | Docker Compose    |
| CI/CD            | GitHub Actions    |
| Cloud            | AWS EC2 (Ubuntu)  |
| Reverse Proxy    | Nginx             |

 ```

📂 Repository Structure

```
.
├── backend/
│   ├── app/
│   ├── server.js
│   └── Dockerfile
│
├── frontend/
│   └── Dockerfile
│
├── docker-compose.yml
├── .github/workflows/deploy.yml
├── nginx.conf
└── README.md
```

💻 Local Development Setup
🔹 Backend Setup
```
cd backend
npm install
```
Update MongoDB credentials in:

app/config/db.config.js

Run backend server:
```
    node server.js
```
🔹 Frontend Setup
```cd frontend
npm install
ng serve --port 8081
```
Modify backend API URL if needed in:
```
src/app/services/tutorial.service.ts
```
Access locally at:

http://localhost:8081

Modify backend API URL if needed in:

src/app/services/tutorial.service.ts

Access locally at:
```
http://localhost:8081    
```


🐳 Docker Deployment
Run Using Docker Compose
docker compose up -d

Verify running containers:
```
docker ps
```
Application will be accessible at:

http://localhost

Or on EC2:
```
http://YOUR_EC2_PUBLIC_IP
```
☁️ Cloud Infrastructure (AWS EC2)
EC2 Configuration

Ubuntu Server

Docker installed

Docker Compose installed

Security Group Rules:

Port 22 (SSH)

Port 80 (HTTP)

Deployment executed using Docker Compose.

🔁 CI/CD Pipeline (GitHub Actions)

The CI/CD pipeline performs the following:

Triggered on push to main

Builds frontend & backend Docker images

Pushes images to Docker Hub

SSH into EC2 server

Pulls latest images

Restarts containers automatically

🐳 Docker Hub Images
```
YOUR_DOCKERHUB_USERNAME/dd-mean-frontend
YOUR_DOCKERHUB_USERNAME/dd-mean-backend
```

🌐 Nginx Reverse Proxy

Nginx serves Angular frontend

Proxies /api requests internally to backend

Entire application accessible via Port 80

Backend port not exposed publicly

📸 Screenshots Included

Screenshots are available in:

/screenshots/


🔐 GitHub Secrets Used

The following secrets are configured securely:

DOCKER_USERNAME

DOCKER_PASSWORD

EC2_HOST

EC2_KEY

No sensitive credentials are stored in the repository.