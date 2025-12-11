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

# 🚀 Local CI/CD Pipeline using Jenkins & Docker

This project demonstrates a **real-world local CI/CD pipeline** where **Jenkins runs inside a Docker container** and automatically builds Docker images from source code stored on **GitHub**.

The project is designed to closely simulate **production-grade CI/CD workflows** and focuses on solving common challenges such as Docker permissions, Jenkins pipeline configuration, and build context management.

---

## 🛠️ Tech Stack

* **Jenkins** (CI/CD automation)
* **Docker** (containerization)
* **Git & GitHub** (version control & SCM)
* **Linux** (container runtime & permissions)
* **Declarative Jenkins Pipeline** (Pipeline as Code)

---

## 📂 Project Structure

```
devops-docker-app/
├── Jenkinsfile
├── app/
│   ├── Dockerfile
│   ├── app.py
│   └── requirements.txt
```

---

## ⚙️ CI/CD Workflow

1. Developer pushes code to **GitHub**
2. Jenkins pulls the repository using **Pipeline script from SCM**
3. Jenkins executes pipeline stages defined in `Jenkinsfile`
4. Docker image is built using a Dockerfile located in a subdirectory
5. Jenkins verifies successful Docker image creation

---

## 🔁 Jenkins Pipeline Stages

* **Checkout Code** – Source code fetched from GitHub
* **Build Docker Image** – Docker image built using custom build context
* **Verify Docker Image** – Image existence validated via Docker CLI

---

## 🔐 Key Implementation Highlights

* Jenkins runs inside a **Docker container**
* Docker socket (`/var/run/docker.sock`) is mounted to allow Jenkins to run Docker commands
* Docker CLI installed inside Jenkins container
* Jenkins user added to Docker group to fix permission issues
* Docker image built from a **subdirectory** using custom Docker build context

---

## 🧠 Challenges & Solutions

| Challenge                    | Solution                                                      |
| ---------------------------- | ------------------------------------------------------------- |
| Jenkins unable to run Docker | Installed Docker CLI and mounted Docker socket                |
| Docker permission denied     | Added Jenkins user to Docker group and fixed socket ownership |
| Jenkinsfile not detected     | Moved Jenkinsfile to repository root                          |
| Dockerfile not found         | Explicitly defined Dockerfile path and build context          |

---

## ✅ Outcome

* Fully functional **local CI/CD pipeline**
* Automated Docker image builds using Jenkins
* Real-world troubleshooting experience with Jenkins and Docker
---

✅ *This project focuses on practical implementation and real troubleshooting rather than theoretical setup.*

Author
Abhay Choudhary 
DevOps Engineer | Jenkins | Docker | Linux
GitHub: https://github.com/abhaykr0316
