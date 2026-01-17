

# CI/CD Pipeline with GitHub Actions and AWS EC2

## Overview

This project implements a simple CI/CD pipeline that automatically builds and deploys a containerised web application to an AWS EC2 instance using GitHub Actions and Docker.

Every push to the `main` branch triggers an automated deployment with no manual steps.

---

## Pipeline Flow

```
GitHub → GitHub Actions → Docker Build → Docker Hub → AWS EC2
```

---

## Tech Stack

* GitHub Actions
* Docker
* AWS EC2 (Amazon Linux)
* Python Flask

---

## How It Works

1. Code is pushed to the `main` branch
2. GitHub Actions builds a Docker image
3. Image is pushed to Docker Hub
4. EC2 pulls the latest image
5. Existing container is replaced automatically

---

## Health Check

* The application exposes a `/health` endpoint
* The deployment verifies the service is running after startup
* Deployment fails if the application is unhealthy

---

## Security

* SSH key-based authentication
* Secrets stored using GitHub Actions Secrets
* No credentials hardcoded in the repository

---

## Limitations

* Single EC2 instance
* No autoscaling or load balancing

---

## Future Improvements

* Infrastructure as Code with Terraform
* Deployment to AWS ECS
* Blue-green deployments

---

## Run Locally

```bash
docker build -t devops-demo .
docker run -p 5000:5000 devops-demo
```

---
