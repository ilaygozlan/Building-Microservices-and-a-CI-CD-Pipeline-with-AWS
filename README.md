# 🧩 AWS CI/CD Microservices Project

## 👥 Group Details
**Group Name:** 2  

**Members:**  
- **Adi Dagan** – 318792579  
- **Ofri Gross** – 322542820  
- **Ilay Gozlan** – 318473295  

---

## 📘 Project Overview
This project demonstrates the implementation of a **complete CI/CD pipeline** for deploying **containerized microservices** using AWS cloud services.

The pipeline automates every stage of the software delivery process — from **development and build** to **deployment and monitoring** — following the **AWS Well-Architected Framework** best practices for security, reliability, and performance efficiency.

---

## ⚙️ AWS Architecture Components

| Layer | AWS Service | Description |
|-------|--------------|-------------|
| **Development** | AWS Cloud9 | Cloud-based IDE for writing, testing, and committing code |
| **Source Control** | AWS CodeCommit | Git-based repository for version management |
| **Build Automation** | AWS CodeBuild | Builds and tests source code, creates Docker images |
| **Containerization** | Docker | Packages applications and dependencies into containers |
| **Image Registry** | Amazon ECR | Secure repository for container images |
| **Orchestration** | Amazon ECS (Fargate) | Runs containers without managing EC2 servers |
| **Traffic Management** | Application Load Balancer (ALB) | Distributes incoming traffic across containers |
| **Deployment Automation** | AWS CodeDeploy | Deploys new images automatically to ECS |
| **Pipeline Management** | AWS CodePipeline | Orchestrates all CI/CD stages automatically |
| **Security** | IAM Roles & Policies | Provides least-privilege access control between services |

---

## 🧭 CI/CD Pipeline Workflow

1. **Developer commits code** → pushed to **CodeCommit**.  
2. **CodePipeline** triggers automatically.  
3. **CodeBuild** compiles the source code, builds Docker images, and runs automated tests.  
4. The image is **pushed to Amazon ECR**.  
5. **CodeDeploy** updates ECS task definitions with the new image.  
6. **ECS Fargate** launches updated containers behind the **Application Load Balancer**.  
7. The **ALB** ensures zero downtime by routing traffic only to healthy tasks.

---

## 🧱 Architecture Diagram

<img width="1536" height="1024" alt="ChatGPT Image Oct 6, 2025, 07_26_27 AM" src="https://github.com/user-attachments/assets/ebb2ca3e-e3d8-4fb7-98de-efb0628e992a" />


---

## 🔐 IAM Roles & Security Setup

| Role | Description |
|------|--------------|
| **CodeBuild Role** | Allows pushing/pulling Docker images to/from ECR |
| **CodeDeploy Role** | Manages ECS service updates and task definitions |
| **CodePipeline Role** | Controls CI/CD stage transitions |
| **ECS Task Role** | Grants runtime permissions to containers |
| **Least Privilege Policy** | Applied to ensure minimal permissions per role |

---

## 🧰 Prerequisites

Before deploying, ensure the following are installed and configured:

- ✅ **Node.js** (v11 or higher)  
- ✅ **Docker** (running locally or via Cloud9)  
- ✅ **AWS CLI** with valid credentials  
- ✅ **AWS Cloud9** environment set up  
- ✅ **ECR repositories** and **ECS cluster** pre-created  

---

## 🚀 Deployment Instructions

### 1. Clone the Repository
```bash
git clone https://git-codecommit.<region>.amazonaws.com/v1/repos/your-repo-name
```

### 2. Build and Push Docker Image
```bash
docker build -t your-app .
docker tag your-app:latest <aws_account_id>.dkr.ecr.<region>.amazonaws.com/your-repo:latest
docker push <aws_account_id>.dkr.ecr.<region>.amazonaws.com/your-repo:latest
```

### 3. Trigger CodePipeline
- Push your latest code to the `main` branch.  
- CodePipeline automatically runs all CI/CD stages.

### 4. Access the Application
- Copy the **DNS name** of the Application Load Balancer from the AWS console.  
- Open it in your browser to verify successful deployment.

---

## 🧩 Monitoring and Logging

- **Amazon CloudWatch:**  
  Monitors ECS task performance, logs, and system metrics.

- **ECS Console:**  
  Displays running services, container health, and task definitions.

- **CodePipeline Dashboard:**  
  Shows live pipeline progress, including build and deploy history.

---

## 🧠 Key Learnings
- Implemented a **fully automated AWS CI/CD pipeline**.  
- Deployed microservices using **Docker + ECS Fargate**.  
- Automated builds, tests, and deployments with **CodePipeline and CodeBuild**.  
- Applied **Well-Architected Framework** principles for cost efficiency, scalability, and security.  
- Gained hands-on experience in **DevOps workflows and AWS developer tools**.

---

## 🏅 AWS Academy Badge

### Ilay Gozlan – AWS Certified Cloud Foundations  
[🎓 View Credential on Credly](https://www.credly.com/badges/5c3ba35d-86a9-460e-aa8e-c6e6e328f429/public_url)

---

## 📊 Summary
This project demonstrates:
- End-to-end **CI/CD automation** using AWS Developer Tools.  
- **Containerized deployment** using ECS with Fargate.  
- **Scalable, secure, and fault-tolerant** microservices infrastructure.  
- Hands-on experience with real-world **DevOps automation**.  

---

### © 2025 – Group 2  
**AWS CI/CD Microservices Project**
