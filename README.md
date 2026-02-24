# Full-Stack Angular & Node.js CRUD Application

This repository contains a containerized Full-Stack application (Angular, Node.js, and MongoDB) deployed on an AWS EC2 instance using Docker, Docker Compose, and Nginx as a reverse proxy.

## 🚀 Architecture Overview
- **Frontend:** Angular 15 (Dockerized with Nginx Alpine)
- **Backend:** Node.js / Express API
- **Database:** MongoDB
- **Proxy:** Nginx (Host-level) directing traffic to containers
- **CI/CD:** GitHub Actions for automated Building and Pushing to Docker Hub

---

## 🛠️ Setup and Deployment Instructions

### 1. Prerequisites
- AWS EC2 Instance (Ubuntu 22.04)
- Docker & Docker Compose installed
- Docker Hub account

### 2. Infrastructure Setup (Nginx)
To allow the application to be accessible on Port 80, the host Nginx acts as a reverse proxy:
1. Ensure AWS Security Groups allow inbound traffic on **Port 80** and **Port 8080**.
2. Update your Nginx sites-available configuration to proxy requests to `localhost:8081` (or your mapped frontend port).

### 3. CI/CD Configuration
Store the following as **GitHub Secrets**:
- `DOCKERHUB_USERNAME`: Your Docker Hub ID
- `DOCKERHUB_TOKEN`: Your Personal Access Token (PAT)

---

## 📸 Deployment Proof & Screenshots

### 1. CI/CD Pipeline Success
Proof of the GitHub Actions workflow successfully building and pushing images.
![CI/CD Execution](screenshots/s1.png)

### 2. Docker Hub Repositories
Verification that the frontend and backend images are hosted on Docker Hub.
![Docker Build and Push](screenshots/s2.png)

### 3. Infrastructure & Container Status
Output of `docker ps` showing all services (Frontend, Backend, MongoDB) are healthy.
![Docker PS Output](screenshots/s3.png)

### 4. Nginx Configuration
The status of the host Nginx service acting as the entry point.
![Nginx Setup](screenshots/s4.png)

### 5. Application UI (Landing Page)
The Angular application accessible via the AWS Public IP.
![Working UI 1](screenshots/s5.png)

### 6. Application Functionality (Database Integration)
Demonstrating CRUD operations and data persistence in MongoDB.
![Working UI 2](screenshots/s6.png)