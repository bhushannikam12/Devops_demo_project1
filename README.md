# 🚀 DevOps Project: Node.js App Deployment on AWS ECS with Terraform and GitHub Actions

This project demonstrates end-to-end DevOps automation to deploy a simple "Hello World" Node.js application using the following stack:

- **Infrastructure as Code (IaC):** Terraform
- **Cloud Platform:** AWS ECS with Fargate (serverless container deployment)
- **Containerization:** Docker
- **CI/CD Pipeline:** GitHub Actions
- **Repository:** [GitHub - DevOps_Project](https://github.com/bhushannikam12/Devops_work)

---

## 📦 Features

- Containerized Node.js application using Docker
- Automated infrastructure provisioning using Terraform
- CI/CD pipeline using GitHub Actions for:
  - Docker image build and push to Docker Hub
  - Infrastructure deployment using Terraform
- Serverless deployment with AWS ECS (Fargate)

---

## 🛠️ Technologies Used

| Tool/Tech        | Purpose                               |
|------------------|----------------------------------------|
| Node.js + Express | Web server for "Hello World" app      |
| Docker           | Containerization                      |
| Terraform        | Infrastructure as Code                |
| AWS ECS (Fargate)| Serverless container orchestration    |
| GitHub Actions   | CI/CD pipeline                        |
| Docker Hub       | Image Registry                        |

---

## 📂 Project Structure
devops_demo_project1/
│
├── app/ # Node.js app files
│ ├── index.js
│ └── package.json
│
├── Dockerfile # Docker build instructions
├── terraform/
│ ├── main.tf # ECS service, task definition, networking
│ ├── variables.tf
│ └── outputs.tf
│
├── .github/
│ └── workflows/
│ └── deploy.yml # GitHub Actions CD pipeline
│
└── README.md

## HOW TO RUN

---

## 🚀 How It Works

### 1. Application
A simple Express.js server that returns "Hello World" on port 3000.

### 2. Docker
The app is containerized with a `Dockerfile` and pushed to Docker Hub.

### 3. Terraform
Provisions:
- ECS Cluster (Fargate launch type)
- Task Definition and ECS Service
- Load balancer, subnets, IAM roles, and security groups

### 4. GitHub Actions
Triggers on push to `main`:
- Builds Docker image
- Pushes image to Docker Hub
- Applies Terraform configuration to deploy app

---

## 🔐 Secrets Configuration

Add the following secrets to your GitHub repository:

| Secret Name            | Description                     |
|------------------------|---------------------------------|
| `DOCKER_USERNAME`      | Docker Hub username             |
| `DOCKER_PASSWORD`      | Docker Hub password or token    |
| `AWS_ACCESS_KEY_ID`    | AWS access key for Terraform    |
| `AWS_SECRET_ACCESS_KEY`| AWS secret key for Terraform    |

---

## 🧪 How to Run

> Make sure Docker, Terraform, and AWS CLI are installed locally (only for manual steps).

### 1. Clone the Repo
git clone https://github.com/bhushannikam12/Devops_work.git
cd devops_demo_project1

### 2. Build and Test Docker locally
docker build -t hello-world-node .
docker run -p 3000:3000 hello-world-node

### 3. Push to GitHub
git add .
git commit -m "Initial automation setup"
git push origin main

### Output
Node.js app deployed to AWS ECS using Fargate
Accessible via public load balancer URL (output from Terraform)
