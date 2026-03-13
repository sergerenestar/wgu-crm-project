---
name: 🏗 Infrastructure Task
about: Terraform, AWS, Docker, or CI/CD work
title: "[INFRA] "
labels: ["infrastructure"]
assignees: ""
---

## 🏗 Infrastructure Task

<!-- Describe the infrastructure work -->

---

## 🔗 Requirement Reference

| Field | Value |
|---|---|
| Requirement ID | `NFR-XXX` |
| Requirement Title | |
| Acceptance Criteria | AC-X, AC-X |

---

## 🎯 Scope

**AWS Services involved:**
- [ ] VPC / Subnets / Security Groups
- [ ] ECS Fargate
- [ ] RDS PostgreSQL
- [ ] ALB (Application Load Balancer)
- [ ] ECR (Container Registry)
- [ ] Secrets Manager
- [ ] CloudWatch
- [ ] S3 (Terraform state)

**Terraform module:**
- `infrastructure/modules/`

**Environment:**
- [ ] Dev
- [ ] Prod
- [ ] Both

---

## ✅ Acceptance Criteria

- [ ] Terraform plan runs with no errors
- [ ] Terraform apply completes successfully in dev
- [ ] Resources verified correct in AWS
- [ ] Changes promoted to prod after dev validation
- [ ] No manually provisioned resources — everything is code (NFR-006 AC-1)

---

## 🔗 Related Issues

- Depends on: #
- Blocks: #
