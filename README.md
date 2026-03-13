# WGU CRM Project

> Enterprise-grade Customer Relationship Management system for MJ Logistics Gaming Company.
> Built as a portfolio project demonstrating full-stack engineering, cloud infrastructure, and software design from real-world business requirements.

This project covers the full engineering lifecycle — from requirements analysis and system design through to implementation, testing, and production deployment on AWS — following practices used in real enterprise environments.

---

## 🏗 Architecture Overview

### 🌐 Network Layer
VPC · Public & Private Subnets · NAT Gateway · Route Tables · Security Groups · AWS Secrets Manager

### 🎨 Frontend
Angular SPA · Nginx Container · AWS ECS (Fargate) · Application Load Balancer

### ⚙️ Backend
Spring Boot REST API · Java 21 · AWS ECS (Fargate) · Multi-AZ capable

### 🗄 Database
RDS PostgreSQL · Private Subnets · No Public Exposure · Encrypted at Rest

### 📦 Containers & Registry
Docker Multi-Stage Builds · AWS ECR · ECS Fargate (no Beanstalk)

### 📊 Observability
CloudWatch Logs · Container Insights · ALB Metrics · Alarms · Dashboards

---

## 🧱 Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Angular |
| Backend | Spring Boot (Java 21) |
| Database | PostgreSQL (AWS RDS) |
| Containers | Docker · AWS ECS Fargate |
| Infrastructure | Terraform (modular) |
| CI/CD | GitHub Actions |
| Image Registry | AWS ECR |
| Secrets | AWS Secrets Manager |
| Observability | CloudWatch |

---

## 🔐 Security Design

- Strict tier isolation: Internet → ALB → ECS → RDS (never direct)
- No public IPs on ECS tasks or RDS instances
- Security Groups enforce least privilege per tier
- NAT Gateway provides controlled outbound access for private resources
- JWT-based authentication with secrets stored in AWS Secrets Manager
- All data remains within the United States (US region only) per requirements

---

## ⚖️ Dev vs Prod Strategy

| Concern | Dev | Prod |
|---|---|---|
| Compute | Single ECS task | ECS Service with desired count |
| Availability | Single AZ | Multi-AZ |
| Scaling | None | ECS Service Auto Scaling |
| Database | Single RDS instance | RDS with Multi-AZ option |
| Cost | Low | Resilient & scalable |
| Approval | Auto deploy | Manual approval gate |

---

## 🚀 CI/CD Pipeline

Three GitHub Actions pipelines cover the full delivery lifecycle:

**PR Check** — triggers on every pull request to `develop`
- Angular unit tests + Spring Boot JUnit tests
- Docker image build validation (no push)

**Dev Deploy** — triggers on merge to `develop`
- Build and push Docker images to AWS ECR
- Terraform plan + apply to dev environment
- Deploy updated task definitions to ECS

**Prod Deploy** — triggers on merge to `main`
- Requires manual approval via GitHub environment protection
- Terraform apply to prod environment
- Post-deploy health check via Spring Boot Actuator

---

## 🛠 Terraform Best Practices Demonstrated

- Remote state in S3 with environment-isolated state files (`dev` vs `prod`)
- Reusable, composable modules with clear input/output boundaries
- Clean separation of networking, compute, database, and observability concerns
- Environment-specific variable files (`.tfvars`) with `.example` templates committed

---

## 📂 Repository Structure

```
wgu-crm-project/
│
├── docs/
│   ├── source-documents/          # Original CRM requirements + system design proposal
│   ├── requirements/              # Interpreted requirements (business, user, functional, non-functional)
│   ├── design/                    # Architecture diagrams, ERD, user flows
│   ├── adr/                       # Architecture Decision Records
│   ├── testing/                   # Test plan and test cases
│   └── videos/                    # Video walkthrough index
│
├── frontend/                      # Angular application
│   ├── src/app/features/          # CRM feature modules (contacts, ticketing, orders, etc.)
│   ├── Dockerfile                 # Multi-stage build → Nginx
│   └── nginx.conf
│
├── backend/                       # Spring Boot REST API
│   ├── src/main/java/             # Controllers, services, repositories, models
│   ├── Dockerfile                 # Multi-stage build → JRE
│   └── pom.xml
│
├── infrastructure/
│   ├── modules/                   # Reusable Terraform modules (ecs, rds, vpc, alb, ecr, cloudwatch)
│   └── environments/
│       ├── dev/                   # Dev environment config
│       └── prod/                  # Prod environment config
│
├── .github/workflows/             # CI/CD pipelines (PR check, dev deploy, prod deploy)
├── docker-compose.yml             # Local development environment
└── README.md
```

---

## 🎯 What This Demonstrates

- **Requirements Engineering** — Translating a real business requirements document into structured technical requirements
- **System Design** — ERD, architecture diagrams, ADRs documenting key decisions
- **Full-Stack Development** — Angular frontend + Spring Boot REST API with role-based access control
- **Cloud Engineering** — Production-style AWS infrastructure with ECS Fargate, RDS, ALB, and VPC
- **Infrastructure as Code** — Modular Terraform with remote state and environment separation
- **Containerisation** — Multi-stage Docker builds with ECR and ECS managed deployment
- **CI/CD** — End-to-end GitHub Actions pipelines with manual prod approval gates
- **Testing** — Unit, integration, and documented test cases mapped to requirements
- **Documentation** — Architecture decisions, design proposals, and video walkthroughs

---

## 🎬 Video Walkthroughs

Short walkthrough videos documenting each phase of the project.
See [docs/videos/README.md](docs/videos/README.md) for the full index.

| # | Topic |
|---|---|
| 01 | Requirements Analysis |
| 02 | System Design Proposal |
| 03 | ERD & Data Modelling |
| 04 | Angular Project Structure |
| 05 | Spring Boot API Design |
| 06 | Docker & Local Dev Setup |
| 07 | Terraform Infrastructure |
| 08 | CI/CD Pipeline Walkthrough |
| 09 | Testing Strategy |
| 10 | Full Feature Demo |

---

## 🚀 Getting Started (Local)

**Prerequisites:** Docker Desktop, Node.js 20+, Java 21+

```bash
# Clone the repo
git clone git@github.com:YOUR_USERNAME/wgu-crm-project.git
cd wgu-crm-project

# Start all services locally
docker compose up --build
```

| Service | URL |
|---|---|
| Frontend | http://localhost:4200 |
| Backend API | http://localhost:8080/api |
| Database | localhost:5432 |

---

## 📖 Documentation

- [CRM Requirements](docs/source-documents/CRM_Requirements.md)
- [System Design Proposal](docs/source-documents/CRM_System_Design_Proposal.md)
- [Requirements Breakdown](docs/requirements/)
- [Architecture Decision Records](docs/adr/)
- [Test Plan](docs/testing/test-plan.md)

---

## 📌 Project Status

| Phase | Status |
|---|---|
| Requirements Analysis | 🟡 In Progress |
| System Design Proposal | 🟡 In Progress |
| Local Dev Environment | ⬜ Not Started |
| Frontend Scaffold | ⬜ Not Started |
| Backend Scaffold | ⬜ Not Started |
| Core Features | ⬜ Not Started |
| Terraform Infrastructure | ⬜ Not Started |
| CI/CD Pipelines | ⬜ Not Started |
| Testing | ⬜ Not Started |
| Video Walkthroughs | ⬜ Not Started |