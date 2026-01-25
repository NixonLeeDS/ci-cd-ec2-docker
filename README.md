# CI/CD Pipeline to AWS EC2

## Overview
This project implements a CI/CD pipeline that automatically builds and deploys a containerised Python web application to an AWS EC2 instance.

Each push to the `main` branch triggers GitHub Actions to run continuous integration and continuous deployment, ensuring the latest version of the application is built, packaged, and deployed with minimal manual intervention.

Infrastructure is provisioned on demand using Terraform and can be destroyed when not in use to control cloud costs.

## Pipeline Flow
- Code push triggers GitHub Actions
- Docker image is built and pushed to a container registry
- EC2 instance pulls the latest image
- Existing container is stopped and replaced
- Application health is validated after deployment

## Tech Stack
- **CI/CD**: GitHub Actions  
- **Infrastructure as Code**: Terraform  
- **Containerisation**: Docker  
- **Cloud**: AWS EC2 (Amazon Linux)  
- **Application**: Python Flask  
