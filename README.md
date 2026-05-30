
# SkillPulse – Three Tier Web Application with CI/CD

## Project Overview

SkillPulse is a three-tier web application built using Go, MySQL, and NGINX, deployed on AWS EC2 using Terraform and automated with GitHub Actions CI/CD.

## Architecture

(image)

## Tech Stack

- AWS EC2
- Terraform
- Docker
- Docker Compose
- GitHub Actions
- Go (Gin)
- MySQL
- NGINX
- Docker Hub

## CI/CD Workflow

Developer Push
↓
GitHub Actions CI
↓
Docker Build & Push
↓
Docker Hub
↓
GitHub Actions CD
↓
SSH to EC2
↓
Docker Compose Deploy
↓
Application Live

## Screenshots

(terraform apply)
(application UI)
(github actions success)

## Key Features

- Infrastructure as Code using Terraform
- Dockerized three-tier architecture
- Automated CI/CD with GitHub Actions
- Docker image deployment via Docker Hub
- Reverse proxy using NGINX
- MySQL persistent storage
- Infrastructure destroy/recreate tested

## Lessons Learned

- Terraform provisioning
- CI/CD automation
- Docker Compose orchestration
- GitHub secrets management
- SSH-based deployments

## Future Improvements

- HTTPS using ACM + ALB
- Kubernetes deployment
- Monitoring with Prometheus/Grafana
- Auto Scaling
