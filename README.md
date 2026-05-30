# 🚀 SkillPulse – Three Tier Web Application with CI/CD on AWS

## 📌 Project Overview

SkillPulse is a **three-tier web application** built using **Go, MySQL, and NGINX**, deployed on **AWS EC2** using **Terraform Infrastructure as Code (IaC)** and automated through **GitHub Actions CI/CD pipelines**.

The project demonstrates a real-world DevOps workflow where every push to the `main` branch automatically triggers:

1. **CI Pipeline**

   * Builds the Go backend Docker image
   * Pushes the image to Docker Hub

2. **CD Pipeline**

   * Connects to AWS EC2 over SSH
   * Pulls the latest image
   * Re-deploys services using Docker Compose

This project was built to demonstrate **Infrastructure as Code, containerization, CI/CD automation, GitHub Actions, Docker, Terraform, and AWS deployment practices**.

---

# 🏗️ Architecture

```text
                    ┌─────────────────────────────┐
                    │          GitHub             │
                    │        Source Code          │
                    └─────────────┬──────────────┘
                                  │ git push
                                  ▼
                      ┌─────────────────────────┐
                      │   GitHub Actions CI     │
                      │ Build + Push Docker Img │
                      └─────────────┬───────────┘
                                    │
                                    ▼
                           ┌────────────────┐
                           │  Docker Hub    │
                           │ Container Repo │
                           └────────┬───────┘
                                    │
                                    ▼
                      ┌─────────────────────────┐
                      │   GitHub Actions CD     │
                      │ SSH Deploy to EC2       │
                      └─────────────┬───────────┘
                                    │
                                    ▼
              ┌─────────────────────────────────────┐
              │          AWS EC2 Instance           │
              │                                     │
              │  ┌─────────┐   ┌──────────────┐    │
              │  │ NGINX   │──►│ Go Backend   │    │
              │  └─────────┘   └──────┬───────┘    │
              │                        │            │
              │                 ┌──────▼───────┐   │
              │                 │ MySQL 8.4    │   │
              │                 └──────────────┘   │
              │                                     │
              │      Docker Compose Deployment      │
              └─────────────────────────────────────┘
```

---

# ⚙️ Tech Stack

### Cloud & Infrastructure

* AWS EC2
* Terraform (Infrastructure as Code)

### DevOps & Automation

* GitHub Actions (CI/CD)
* Docker
* Docker Compose
* Docker Hub

### Application Stack

* Go (Gin Framework)
* MySQL 8.4
* NGINX

### Version Control

* Git
* GitHub

---

# 📂 Project Structure

```text
SkillPulse/
│
├── backend/                  # Go REST API
├── frontend/                 # HTML/CSS/JS frontend
├── mysql/                    # Database initialization
├── nginx/                    # Reverse proxy config
├── terraform/                # Infrastructure provisioning
│
├── docker-compose.yml        # Multi-container orchestration
├── .github/workflows/
│   ├── ci.yml                # Build & Push pipeline
│   └── cd.yml                # Deployment pipeline
│
└── README.md
```

---

# 🔁 CI/CD Workflow

### Continuous Integration (CI)

On every push to `main`:

* GitHub Actions checks out the repository
* Docker image is built from the Go backend
* Image is pushed to Docker Hub

### Continuous Deployment (CD)

After CI succeeds:

* GitHub Actions SSHs into AWS EC2
* Pulls latest repository updates
* Pulls latest Docker image
* Restarts services using Docker Compose

Deployment command executed:

```bash
cd ~/skillpulse
git pull origin main
docker compose pull
docker compose up -d
docker image prune -f
```

---

# ☁️ Infrastructure Provisioning

Infrastructure is provisioned using **Terraform**.

Terraform automates:

* EC2 Instance creation
* Security Groups
* SSH Key generation
* Docker installation (via user_data)
* Docker Compose setup
* Repository bootstrap

Example:

```bash
terraform init
terraform apply
```

Destroy infrastructure:

```bash
terraform destroy
```

---

# 🐳 Containerized Services

The application runs as **three containers**:

### NGINX

* Serves frontend UI
* Reverse proxies backend API

### Go Backend

* REST API
* Business logic

### MySQL

* Stores skill tracking data
* Persistent Docker volume

Container orchestration:

```bash
docker compose up -d
```

---

# 📸 Screenshots

## Application Dashboard

*Add screenshot here*

Example:

```text
screenshots/dashboard.png
```

---

## GitHub Actions CI/CD

*Add screenshot here*

Example:

```text
screenshots/github-actions-success.png
```

---

## Terraform Apply

*Add screenshot here*

Example:

```text
screenshots/terraform-apply.png
```

---

## Running Docker Containers

*Add screenshot here*

Example:

```text
screenshots/docker-ps.png
```

---

## API Response

*Add screenshot here*

Example:

```text
screenshots/api-response.png
```

---

# 🧪 Validation Performed

✅ Terraform provisioning tested

✅ Docker Compose deployment tested

✅ GitHub Actions CI/CD validated

✅ Docker image deployment validated

✅ Frontend deployment validated

✅ API endpoints validated

✅ MySQL persistence verified

✅ Destroy → Recreate repeatability tested

---

# 🎯 Key Features

* Infrastructure as Code using Terraform
* Fully containerized three-tier architecture
* Automated CI/CD with GitHub Actions
* Docker image deployment using Docker Hub
* NGINX reverse proxy
* MySQL persistent storage
* Automated EC2 deployment via SSH
* End-to-end deployment validation

---

# 📚 Key Learnings

This project helped strengthen hands-on experience in:

* Terraform Infrastructure as Code
* AWS EC2 provisioning
* Docker containerization
* Docker Compose orchestration
* GitHub Actions automation
* CI/CD pipeline implementation
* GitHub Secrets management
* Linux server operations
* Reverse proxy configuration with NGINX

---

# 🔮 Future Improvements

* HTTPS using SSL/TLS
* Load Balancer integration
* Kubernetes deployment (EKS)
* Monitoring with Prometheus + Grafana
* Centralized logging
* Auto Scaling infrastructure
* Blue-Green deployment strategy

---

# 👨‍💻 Author

**Sukesh Kumar**

GitHub: https://github.com/subaransukesh05-dot
