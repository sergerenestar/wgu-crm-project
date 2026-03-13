# GitHub Projects — Board Setup Guide

> **Project:** WGU CRM — MJ Logistics Gaming Company
> **Repo:** `github.com/sergerenestar/wgu-crm-project`
> **Requirements Source:** `docs/requirements/` — all requirement IDs below map exactly to those files

---

## 🗂 Board Columns

| Column | Purpose |
|---|---|
| **📥 Backlog** | All issues not yet started |
| **🔨 In Progress** | Actively being worked on |
| **👀 In Review** | PR open, awaiting check |
| **✅ Done** | Merged and complete |

---

## 🏷 Labels

Create at `github.com/YOUR_USERNAME/wgu-crm-project/labels`

| Label | Hex Color | Purpose |
|---|---|---|
| `user-story` | `#0075ca` | Feature work |
| `bug` | `#d73a4a` | Something broken |
| `infrastructure` | `#e4e669` | Terraform / AWS / Docker |
| `documentation` | `#cfd3d7` | Docs, ADRs, diagrams, videos |
| `frontend` | `#a2eeef` | Angular work |
| `backend` | `#7057ff` | Spring Boot work |
| `testing` | `#008672` | Test coverage |
| `ci-cd` | `#e99695` | GitHub Actions pipelines |
| `blocked` | `#b60205` | Blocked by dependency |
| `good-first-issue` | `#7fc97f` | Simple starting point |

---

## 🏁 Milestones



| # | Milestone | Requirement Coverage |
|---|---|---|
| 1 | `M1 — Requirements & Design` | All BR / UR / FR / NFR |
| 2 | `M2 — Local Dev Environment` | NFR-006 |
| 3 | `M3 — Authentication & RBAC` | UR-001, UR-006, NFR-002 |
| 4 | `M4 — Contact & Business Management` | BR-001, FR-001 |
| 5 | `M5 — Ticketing System` | BR-003, FR-002 |
| 6 | `M6 — Opportunity & Pipeline` | BR-002, FR-003 |
| 7 | `M7 — Quoting & Orders` | BR-005, FR-004 |
| 8 | `M8 — Contracts & Forecasting` | BR-005, FR-005, FR-006 |
| 9 | `M9 — Reporting & Dashboards` | BR-004 |
| 10 | `M10 — Infrastructure & CI/CD` | NFR-001, NFR-002, NFR-004, NFR-005, NFR-006 |
| 11 | `M11 — Testing` | NFR-006 AC-6 |
| 12 | `M12 — Video Walkthroughs` | All |

---

## 📌 Issues by Milestone

---

### 🗂 M1 — Requirements & Design

> Source files: `docs/requirements/` and `docs/source-documents/`

| # | Issue Title | Template | Labels | Req ID | AC |
|---|---|---|---|---|---|
| 1 | `[DOCS] Upload and verify CRM Requirements source document` | Documentation | `documentation` | All | — |
| 2 | `[DOCS] Write and format business-requirements.md` | Documentation | `documentation` | BR-001→BR-005 | All AC |
| 3 | `[DOCS] Write and format user-requirements.md` | Documentation | `documentation` | UR-001→UR-006 | All AC |
| 4 | `[DOCS] Write and format functional-requirements.md` | Documentation | `documentation` | FR-001→FR-006 | All AC |
| 5 | `[DOCS] Write and format non-functional-requirements.md` | Documentation | `documentation` | NFR-001→NFR-006 | All AC |
| 6 | `[DOCS] Write CRM System Design Proposal` | Documentation | `documentation` | All | — |
| 7 | `[DOCS] Create ERD — contacts, businesses, tickets, opportunities, orders, contracts` | Documentation | `documentation`, `backend` | FR-001, FR-002, FR-004, FR-005 | AC-1, AC-3 |
| 8 | `[DOCS] Create system architecture diagram — AWS ECS, RDS, ALB, VPC` | Documentation | `documentation`, `infrastructure` | NFR-002, NFR-004, NFR-005 | AC-1→AC-3 |
| 9 | `[DOCS] Create user flow diagrams — login, contact creation, ticket lifecycle` | Documentation | `documentation`, `frontend` | UR-001, UR-005, FR-001, FR-002 | AC-1→AC-6 |
| 10 | `[DOCS] Write ADR-001 — Angular + Spring Boot choice` | Documentation | `documentation` | NFR-006 | AC-3, AC-4 |
| 11 | `[DOCS] Write ADR-002 — AWS ECS deployment strategy` | Documentation | `documentation`, `infrastructure` | NFR-004, NFR-005 | AC-1, AC-2 |
| 12 | `[DOCS] Write ADR-003 — PostgreSQL database choice` | Documentation | `documentation`, `backend` | NFR-001 | AC-1 |
| 13 | `[DOCS] Write ADR-004 — Terraform infrastructure strategy` | Documentation | `documentation`, `infrastructure` | NFR-006 | AC-1, AC-2 |
| 14 | `[DOCS] Write ADR-005 — Docker multi-stage build strategy` | Documentation | `documentation`, `infrastructure` | NFR-006 | AC-7 |

---

### 🗂 M2 — Local Dev Environment

> Requirement: **NFR-006 — Maintainability and Extensibility**

| # | Issue Title | Template | Labels | Req ID | AC |
|---|---|---|---|---|---|
| 15 | `[INFRA] Configure docker-compose — frontend, backend, PostgreSQL` | Infrastructure | `infrastructure` | NFR-006 | AC-7 |
| 16 | `[INFRA] Set up PostgreSQL container with schema and seed data` | Infrastructure | `infrastructure`, `backend` | FR-001 | AC-1 |
| 17 | `[STORY] Scaffold Angular project with CRM feature modules` | User Story | `frontend` | NFR-006 | AC-3 |
| 18 | `[STORY] Scaffold Spring Boot project with layered package structure` | User Story | `backend` | NFR-006 | AC-4 |
| 19 | `[DOCS] Document local setup steps in README` | Documentation | `documentation` | NFR-006 | AC-7 |

---

### 🗂 M3 — Authentication & RBAC

> Requirements: **UR-001 — Role-Based Access Control · UR-006 — Active Directory Integration · NFR-002 — Security**

| # | Issue Title | Template | Labels | Req ID | AC |
|---|---|---|---|---|---|
| 20 | `[STORY] Implement JWT authentication in Spring Boot Security` | User Story | `backend` | UR-006, NFR-002 | UR-006 AC-1, NFR-002 AC-6 |
| 21 | `[STORY] Integrate Active Directory / SSO login` | User Story | `backend` | UR-006 | AC-1, AC-2, AC-3 |
| 22 | `[STORY] Log failed login attempts and enforce account lockout` | User Story | `backend` | UR-006 | AC-4 |
| 23 | `[STORY] Implement role-based access control on all API endpoints` | User Story | `backend` | UR-001, NFR-002 | UR-001 AC-1→AC-3, NFR-002 AC-7 |
| 24 | `[STORY] Role permission management by administrators (no code changes)` | User Story | `backend` | UR-001 | AC-2 |
| 25 | `[STORY] Permission changes take effect immediately without re-login` | User Story | `backend` | UR-001 | AC-6 |
| 26 | `[STORY] Build Angular login page with auth guard and route protection` | User Story | `frontend` | UR-001, UR-006 | UR-001 AC-3 |
| 27 | `[STORY] Implement soft delete — hide record, retain in DB` | User Story | `backend` | UR-001, NFR-003 | UR-001 AC-5, NFR-003 AC-2 |
| 28 | `[STORY] Implement hard delete — restricted to admin role, fully logged` | User Story | `backend` | UR-001, NFR-003 | UR-001 AC-4, NFR-003 AC-3 |
| 29 | `[INFRA] Store JWT secret in AWS Secrets Manager` | Infrastructure | `infrastructure` | NFR-002 | AC-6 |
| 30 | `[INFRA] Log all auth events and permission failures to CloudWatch` | Infrastructure | `infrastructure` | NFR-002 | AC-8 |

---

### 🗂 M4 — Contact & Business Management

> Requirements: **BR-001 — Consolidated Contact and Business Management · FR-001 — Contact and Business Entity Management**

| # | Issue Title | Template | Labels | Req ID | AC |
|---|---|---|---|---|---|
| 31 | `[STORY] Create business entity with name, address, phone, custom fields` | User Story | `frontend`, `backend` | FR-001 | AC-1 |
| 32 | `[STORY] Duplicate detection on new business entry` | User Story | `frontend`, `backend` | BR-001, FR-001 | BR-001 AC-2, FR-001 AC-2 |
| 33 | `[STORY] Link contacts to one or more businesses and assign roles` | User Story | `frontend`, `backend` | BR-001, FR-001 | BR-001 AC-3, FR-001 AC-3 |
| 34 | `[STORY] Preserve contact history when moving between businesses or roles` | User Story | `backend` | BR-001, FR-001 | BR-001 AC-4, FR-001 AC-4 |
| 35 | `[STORY] Save and flag partial contact entries for follow-up` | User Story | `frontend`, `backend` | FR-001, UR-005 | FR-001 AC-5, UR-005 AC-4 |
| 36 | `[STORY] Tag interactions to contacts during active calls` | User Story | `frontend`, `backend` | BR-003, FR-001 | FR-001 AC-6 |
| 37 | `[STORY] Categorize contacts by type — visible and filterable` | User Story | `frontend`, `backend` | FR-001 | AC-7 |
| 38 | `[STORY] Manage contact communication and marketing preferences` | User Story | `frontend`, `backend` | UR-003 | AC-1→AC-5 |
| 39 | `[STORY] Real-time data access for remote and on-site users` | User Story | `backend`, `infrastructure` | BR-001 | AC-5 |

---

### 🗂 M5 — Ticketing System

> Requirements: **BR-003 — Centralized Activity and Communication Management · FR-002 — Ticketing System and Workflow**

| # | Issue Title | Template | Labels | Req ID | AC |
|---|---|---|---|---|---|
| 40 | `[STORY] Create ticket linked to contact, business, date, time, and assigned user` | User Story | `frontend`, `backend` | FR-002 | AC-1, AC-2 |
| 41 | `[STORY] Unique ticket identifier — no two tickets share the same ID` | User Story | `backend` | FR-002 | AC-7 |
| 42 | `[STORY] Implement ticket workflow stages — Open, In Progress, Pending, Resolved` | User Story | `frontend`, `backend` | FR-002 | AC-4 |
| 43 | `[STORY] Auto-capture email replies and append to ticket thread` | User Story | `backend` | BR-003, FR-002 | BR-003 AC-2, FR-002 AC-3 |
| 44 | `[STORY] Audit trail on all ticket status changes and user actions` | User Story | `backend` | BR-003, FR-002, NFR-003 | FR-002 AC-5, NFR-003 AC-1 |
| 45 | `[STORY] Escalate, reassign, and link related tickets` | User Story | `frontend`, `backend` | FR-002 | AC-6 |
| 46 | `[STORY] Integrate CRM activity records with Microsoft Exchange / Outlook` | User Story | `backend` | BR-003 | AC-2 |
| 47 | `[STORY] Activity records cannot be permanently deleted by standard users` | User Story | `backend` | BR-003 | AC-5 |

---

### 🗂 M6 — Opportunity & Pipeline

> Requirements: **BR-002 — Sales Tracking and Pipeline Visibility · FR-003 — Opportunity and Pipeline Management**

| # | Issue Title | Template | Labels | Req ID | AC |
|---|---|---|---|---|---|
| 48 | `[STORY] Create opportunity linked to contact and business` | User Story | `frontend`, `backend` | FR-003 | AC-1 |
| 49 | `[STORY] Progress opportunity through configurable pipeline stages` | User Story | `frontend`, `backend` | BR-002, FR-003 | BR-002 AC-1, FR-003 AC-2 |
| 50 | `[STORY] Record win and loss outcomes with reasons and competitor details` | User Story | `frontend`, `backend` | BR-002, FR-003 | BR-002 AC-2, FR-003 AC-3 |
| 51 | `[STORY] Competitive analysis and product comparison on opportunities` | User Story | `frontend`, `backend` | FR-003 | AC-3 |
| 52 | `[STORY] Discount approval workflow before applying to quote` | User Story | `backend` | FR-003 | AC-4 |
| 53 | `[STORY] Pipeline dashboard — filterable by stage, owner, product, period` | User Story | `frontend` | BR-002, FR-003 | BR-002 AC-5, FR-003 AC-5 |
| 54 | `[STORY] View full activity history and communications from opportunity record` | User Story | `frontend` | FR-003 | AC-6 |

---

### 🗂 M7 — Quoting & Orders

> Requirements: **BR-005 — Order and Contract Lifecycle Management · FR-004 — Quoting and Order Management**

| # | Issue Title | Template | Labels | Req ID | AC |
|---|---|---|---|---|---|
| 55 | `[STORY] Generate quote with pricing, discounts, tax, freight, and currency` | User Story | `frontend`, `backend` | BR-005, FR-004 | BR-005 AC-1, FR-004 AC-1 |
| 56 | `[STORY] Maintain price catalog — auto-applied when products added to quote` | User Story | `backend` | FR-004 | AC-2 |
| 57 | `[STORY] Electronic signature support on quotes` | User Story | `frontend`, `backend` | FR-004 | AC-3 |
| 58 | `[STORY] Convert confirmed quote to order in single action — no re-entry` | User Story | `backend` | BR-005, FR-004 | BR-005 AC-2, FR-004 AC-4 |
| 59 | `[STORY] Reordering, partial ordering, and real-time inventory checks` | User Story | `backend` | BR-005, FR-004 | BR-005 AC-5, FR-004 AC-5 |
| 60 | `[STORY] Customer self-service portal for viewing and managing orders` | User Story | `frontend`, `backend` | FR-004 | AC-6 |
| 61 | `[STORY] Version-controlled quote and order records with full change history` | User Story | `backend` | BR-005, FR-004, NFR-003 | BR-005 AC-6, FR-004 AC-7 |

---

### 🗂 M8 — Contracts & Forecasting

> Requirements: **BR-005 — Order and Contract Lifecycle · FR-005 — Contract Management · FR-006 — Forecasting**

| # | Issue Title | Template | Labels | Req ID | AC |
|---|---|---|---|---|---|
| 62 | `[STORY] Create contract linked to opportunity and business` | User Story | `frontend`, `backend` | BR-005, FR-005 | BR-005 AC-3, FR-005 AC-1 |
| 63 | `[STORY] Approval and authorization workflow before contract signing` | User Story | `backend` | BR-005, FR-005 | BR-005 AC-4, FR-005 AC-2 |
| 64 | `[STORY] Electronic contract signing` | User Story | `frontend`, `backend` | FR-005 | AC-3 |
| 65 | `[STORY] Track contract terms, start dates, end dates, and renewal windows` | User Story | `backend` | FR-005 | AC-4 |
| 66 | `[STORY] Automated renewal and termination alerts to assigned users` | User Story | `backend` | FR-005 | AC-5 |
| 67 | `[STORY] Retain expired and terminated contracts as historical records` | User Story | `backend` | FR-005, NFR-003 | FR-005 AC-6, NFR-003 AC-2 |
| 68 | `[STORY] Auto-generate forecasts from pipeline data and historical close rates` | User Story | `backend` | FR-006 | AC-1 |
| 69 | `[STORY] Manager forecast adjustments with recorded reason` | User Story | `frontend`, `backend` | BR-002, FR-006 | BR-002 AC-4, FR-006 AC-2 |
| 70 | `[STORY] Forecast periods — weekly, monthly, quarterly, annually` | User Story | `frontend` | FR-006 | AC-3 |
| 71 | `[STORY] Baseline snapshot and forecast comparison` | User Story | `backend` | FR-006 | AC-4 |
| 72 | `[STORY] Product-level forecasting broken down by product line` | User Story | `backend` | FR-006 | AC-5 |
| 73 | `[STORY] Currency adjustments on forecasts for foreign currency deals` | User Story | `backend` | BR-002, FR-006 | BR-002 AC-4, FR-006 AC-6 |
| 74 | `[STORY] Machine-assisted forecast alongside manager view` | User Story | `backend` | FR-006 | AC-7 |

---

### 🗂 M9 — Reporting & Dashboards

> Requirements: **BR-004 — Reporting and Business Intelligence**

| # | Issue Title | Template | Labels | Req ID | AC |
|---|---|---|---|---|---|
| 75 | `[STORY] Predefined reports — sales performance, pipeline status, activity summary` | User Story | `frontend`, `backend` | BR-004 | AC-1 |
| 76 | `[STORY] Custom report builder with filtering and query interface` | User Story | `frontend`, `backend` | BR-004 | AC-2 |
| 77 | `[STORY] Save and reuse report filters per user` | User Story | `frontend`, `backend` | BR-004 | AC-2 |
| 78 | `[STORY] Executive summary dashboard with key business metrics` | User Story | `frontend` | BR-004 | AC-3 |
| 79 | `[STORY] Export reports to CSV and PDF` | User Story | `backend` | BR-004 | AC-4 |
| 80 | `[STORY] Role-scoped report data — users see only their department's data` | User Story | `backend` | BR-004, UR-001 | BR-004 AC-5, UR-001 AC-3 |
| 81 | `[STORY] Historical data reporting for trend analysis across periods` | User Story | `backend` | BR-004 | AC-6 |

---

### 🗂 M10 — Infrastructure & CI/CD

> Requirements: **NFR-001 · NFR-002 · NFR-004 · NFR-005 · NFR-006**

| # | Issue Title | Template | Labels | Req ID | AC |
|---|---|---|---|---|---|
| 82 | `[INFRA] Build Terraform VPC module — subnets, NAT gateway, route tables` | Infrastructure | `infrastructure` | NFR-002 | AC-1→AC-3 |
| 83 | `[INFRA] Build Terraform Security Groups — least privilege per tier` | Infrastructure | `infrastructure` | NFR-002 | AC-3 |
| 84 | `[INFRA] Build Terraform ECS module — Fargate, multi-AZ, task definitions` | Infrastructure | `infrastructure` | NFR-004, NFR-005 | NFR-004 AC-1, NFR-005 AC-2 |
| 85 | `[INFRA] Build Terraform RDS module — PostgreSQL, private subnet, encrypted` | Infrastructure | `infrastructure` | NFR-001, NFR-002, NFR-005 | NFR-001 AC-1, NFR-002 AC-4, NFR-005 AC-4 |
| 86 | `[INFRA] Build Terraform ALB module — health checks, routing rules` | Infrastructure | `infrastructure` | NFR-005 | AC-3 |
| 87 | `[INFRA] Build Terraform ECR module — image registry` | Infrastructure | `infrastructure` | NFR-006 | AC-1 |
| 88 | `[INFRA] Build Terraform Secrets Manager module` | Infrastructure | `infrastructure` | NFR-002 | AC-6 |
| 89 | `[INFRA] Build Terraform CloudWatch module — logs, alarms, dashboards` | Infrastructure | `infrastructure` | NFR-004 | AC-5 |
| 90 | `[INFRA] Configure Terraform S3 remote state backend` | Infrastructure | `infrastructure` | NFR-006 | AC-1 |
| 91 | `[INFRA] Configure dev environment — single AZ, cost-efficient` | Infrastructure | `infrastructure` | NFR-006 | AC-1 |
| 92 | `[INFRA] Configure prod environment — multi-AZ, high availability` | Infrastructure | `infrastructure` | NFR-005 | AC-1, AC-2 |
| 93 | `[INFRA] Docker multi-stage build — Angular frontend → Nginx` | Infrastructure | `infrastructure`, `frontend` | NFR-006 | AC-7 |
| 94 | `[INFRA] Docker multi-stage build — Spring Boot → JRE Alpine` | Infrastructure | `infrastructure`, `backend` | NFR-006 | AC-7 |
| 95 | `[CI/CD] Build PR check pipeline — frontend tests, backend tests, docker build` | Infrastructure | `ci-cd` | NFR-006 | AC-6 |
| 96 | `[CI/CD] Build dev deploy pipeline — ECR push, Terraform apply, ECS deploy` | Infrastructure | `ci-cd` | NFR-006 | AC-1 |
| 97 | `[CI/CD] Build prod deploy pipeline — manual approval gate, health check` | Infrastructure | `ci-cd` | NFR-005, NFR-006 | NFR-005 AC-6, NFR-006 AC-1 |
| 98 | `[INFRA] Verify all data stays in US regions — data flow review` | Infrastructure | `infrastructure` | NFR-001 | AC-1, AC-2, AC-5 |

---

### 🗂 M11 — Testing

> Requirement: **NFR-006 AC-6 — 70% minimum unit test coverage on business logic**

| # | Issue Title | Template | Labels | Req ID | AC |
|---|---|---|---|---|---|
| 99 | `[STORY] Unit tests — Spring Boot service layer (contact, ticket, opportunity)` | User Story | `testing`, `backend` | NFR-006 | AC-6 |
| 100 | `[STORY] Unit tests — Angular components and services` | User Story | `testing`, `frontend` | NFR-006 | AC-6 |
| 101 | `[STORY] Integration tests — REST API endpoints` | User Story | `testing`, `backend` | NFR-006 | AC-6 |
| 102 | `[STORY] Load testing — validate 500 concurrent users` | User Story | `testing`, `infrastructure` | UR-004 | AC-1, AC-2, AC-5 |
| 103 | `[DOCS] Write test plan mapped to all requirement IDs` | Documentation | `documentation`, `testing` | All | — |
| 104 | `[DOCS] Document test cases — Contact & Business Management (FR-001)` | Documentation | `documentation`, `testing` | FR-001 | All AC |
| 105 | `[DOCS] Document test cases — Ticketing System (FR-002)` | Documentation | `documentation`, `testing` | FR-002 | All AC |
| 106 | `[DOCS] Document test cases — RBAC and Authentication (UR-001, UR-006)` | Documentation | `documentation`, `testing` | UR-001, UR-006 | All AC |
| 107 | `[DOCS] Document test cases — Data Residency and Security (NFR-001, NFR-002)` | Documentation | `documentation`, `testing` | NFR-001, NFR-002 | All AC |

---

### 🗂 M12 — Video Walkthroughs

> Index: `docs/videos/README.md`

| # | Issue Title | Template | Labels | Video # |
|---|---|---|---|---|
| 108 | `[DOCS] Record Video 01 — Requirements Analysis walkthrough` | Documentation | `documentation` | 01 |
| 109 | `[DOCS] Record Video 02 — System Design Proposal walkthrough` | Documentation | `documentation` | 02 |
| 110 | `[DOCS] Record Video 03 — ERD and Data Modelling walkthrough` | Documentation | `documentation` | 03 |
| 111 | `[DOCS] Record Video 04 — Angular project structure walkthrough` | Documentation | `documentation`, `frontend` | 04 |
| 112 | `[DOCS] Record Video 05 — Spring Boot API design walkthrough` | Documentation | `documentation`, `backend` | 05 |
| 113 | `[DOCS] Record Video 06 — Docker and local dev setup walkthrough` | Documentation | `documentation`, `infrastructure` | 06 |
| 114 | `[DOCS] Record Video 07 — Terraform infrastructure walkthrough` | Documentation | `documentation`, `infrastructure` | 07 |
| 115 | `[DOCS] Record Video 08 — CI/CD pipeline walkthrough` | Documentation | `documentation`, `ci-cd` | 08 |
| 116 | `[DOCS] Record Video 09 — Testing strategy walkthrough` | Documentation | `documentation`, `testing` | 09 |
| 117 | `[DOCS] Record Video 10 — Full feature demo` | Documentation | `documentation` | 10 |

---

## 💬 Commit Message Convention

Every commit links to its issue number. Format:

```
feat: implement contact duplicate detection (#32)
fix: correct JWT token expiry (#20)
docs: write functional requirements (#4)
infra: add ECS Fargate Terraform module (#84)
test: add Spring Boot service layer unit tests (#99)
```

Use `Closes #32` in your PR body — GitHub automatically closes the issue on merge.

---

## 📋 Requirements Traceability Summary

| Requirement File | IDs | Issues Covered |
|---|---|---|
| `business-requirements.md` | BR-001→BR-005 | #31–#81 |
| `user-requirements.md` | UR-001→UR-006 | #20–#30, #38, #80, #102 |
| `functional-requirements.md` | FR-001→FR-006 | #31–#81 |
| `non-functional-requirements.md` | NFR-001→NFR-006 | #82–#98 |
