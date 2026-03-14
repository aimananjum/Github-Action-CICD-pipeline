# 🚀 CI/CD Pipeline with GitHub Actions, Docker, and AWS EC2

This project demonstrates a complete **DevOps CI/CD pipeline** using:

- GitHub Actions
- Docker
- DockerHub
- AWS EC2
- Flask (Python)

The pipeline automatically builds and pushes a Docker image whenever code is pushed to GitHub.

---

# 📌 Project Architecture

Developer pushes code → GitHub Actions triggers pipeline → Docker image builds → Image pushed to DockerHub → EC2 pulls image → Application runs in container

---

# 🧰 Tech Stack

- Python (Flask)
- Docker
- GitHub Actions
- DockerHub
- AWS EC2
- Linux (Ubuntu)

---

# ⚙️ Application Overview

The application is a simple **Flask web service** 

- Docker Implementation
The application uses a multi-stage Docker build to reduce image size.
- Docker stages:
- Builder stage
- Installs Python dependencies
- Production stage
- Copies installed packages
- Runs Flask app

---

# 📌 CI/CD Pipeline
The pipeline is implemented using GitHub Actions.
Workflow file:
.github/workflows/deploy.yml
- Test Stage
Installs dependencies and runs tests.
- Build Stage
Builds Docker image.
- Push Stage
Pushes image to DockerHub.
- Deploy Notification
Indicates successful deployment.

---

# 🛠️ Setup Instructions
- clone repo & build image & run conatiner & test
- git clone https://github.com/aimananjum/Github-Action-CICD-pipeline.git
- cd Github-Action-CICD-pipeline
- docker build -t devops-webapp .
- curl http://localhost:5000
- docker run -d -p 5000:5000 devops-webapp

---

# ☁️ Deployment
- The Docker image is pushed to DockerHub:
- aimananjum/devops-webapp:latest
- It can be deployed on any server using:
- docker pull aimananjum/devops-webapp:latest
- docker run -d -p 5000:5000 aimananjum/devops-webapp
