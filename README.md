# CI/CD Pipeline to AWS EC2

## Overview
This project implements a simple CI/CD pipeline that automatically builds and deploys a containerised web application to an AWS EC2 instance.

Every push to the `main` branch triggers GitHub Actions to run both continuous integration and continuous deployment, ensuring the latest version of the application is built, packaged, and deployed without manual steps.

---

## Pipeline Flow
- Code push triggers GitHub Actions
- Docker image is built and pushed to a registry
- EC2 pulls the latest image
- Existing container is replaced
- Application health is validated after deployment

This setup demonstrates core DevOps fundamentals such as CI/CD automation, containerisation, and cloud-based deployment.

---

## Tech Stack
- **CI/CD**: GitHub Actions  
- **Containerisation**: Docker  
- **Cloud**: AWS EC2 (Amazon Linux)  
- **Application**: Python Flask  
