# DevOps Docker Web App

🏆 **This is a simple web application containerized with Docker.**  
It demonstrates the complete workflow from code → Docker image → running container → browser access.

---

## Features

- Web application 
- Dockerized for portability
- Can run locally or in any Docker-enabled environment

---

## Prerequisites

- [Docker](https://www.docker.com/get-started) installed
- Git (optional, if cloning the repository)

---

## Project Structure

devops-project/
├── Dockerfile
├── app/ (your application files)
├── README.md
└── ...other files

---

## Steps to Run Locally

1. **Build Docker image**
```bash
docker build -t devops-docker-app .
Run container

docker run -p 8080:80 devops-docker-app

Access app in browser
http://localhost:8080

Steps to Push to Docker Hub
Login to Docker Hub

docker login
Tag your image

docker tag devops-docker-app <your-dockerhub-username>/devops-docker-app:latest
Push image to Docker Hub

docker push <your-dockerhub-username>/devops-docker-app:latest
Run your image from Docker Hub

docker run -p 8080:80 <your-dockerhub-username>/devops-docker-app:latest

Useful Docker Commands
List images:

docker images
List running containers:
docker ps

Stop a container:
docker stop <container-id>


Author
Abhay Choudhary – DevOps Enthusiast
GitHub: https://github.com/abhaykr0316
