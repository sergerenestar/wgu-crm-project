# 🛡 Non-Functional Requirements

> **Source:** *Interpreted from the MJ Logistics Gaming Company CRM
> Requirements document*\
> These requirements define **the quality attributes, constraints, and
> operational characteristics the system must meet.**

------------------------------------------------------------------------

# 📊 Requirements Overview

  ID            Requirement                          Domain
  ------------- ------------------------------------ -------------
  **NFR-001**   Data Residency and Compliance        Compliance
  **NFR-002**   Security and Access Control          Security
  **NFR-003**   Audit Trail and Data Integrity       Governance
  **NFR-004**   Scalability and Performance          Performance
  **NFR-005**   Availability and Disaster Recovery   Reliability
  **NFR-006**   Maintainability and Extensibility    Engineering

------------------------------------------------------------------------

# 🇺🇸 NFR-001 --- Data Residency and Compliance

### Description

MJ Logistics operates in a **regulated environment** where the location
and handling of data is subject to legal requirements.

All data collected, processed, and stored by the CRM must **remain
within the United States**.\
The system must be designed with **data protection compliance built in
from the ground up**, not added as an afterthought.

------------------------------------------------------------------------

### Acceptance Criteria

  -----------------------------------------------------------------------
  ID                                  Requirement
  ----------------------------------- -----------------------------------
  AC-1                                All application data is stored in
                                      AWS infrastructure provisioned
                                      exclusively in US regions
                                      (us-east-1 or us-west-2)

  AC-2                                No data is transmitted to or
                                      processed in servers outside the
                                      United States unless explicitly
                                      approved in writing

  AC-3                                The system complies with applicable
                                      US data protection regulations

  AC-4                                Data residency is enforced at the
                                      infrastructure level via Terraform
                                      configuration, not relying solely
                                      on application-level controls

  AC-5                                A data flow diagram documents how
                                      data moves through the system and
                                      confirms no cross-border transfers
                                      occur
                                      
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 🔐 NFR-002 --- Security and Access Control

### Description

The CRM will hold **sensitive business, contact, and commercial data**.

The system must be **secure by default at every layer --- network,
application, and data**.\
Security must be enforced through **infrastructure design**, not just
application logic.

------------------------------------------------------------------------

### Acceptance Criteria

  -----------------------------------------------------------------------
  ID                                  Requirement
  ----------------------------------- -----------------------------------
  AC-1                                No ECS tasks or RDS instances have
                                      public IP addresses

  AC-2                                All traffic enters the system
                                      through the Application Load
                                      Balancer only

  AC-3                                Security Groups enforce
                                      least-privilege rules: internet →
                                      ALB only, ALB → application tier
                                      only, application → database only

  AC-4                                All data at rest in RDS is
                                      encrypted using AWS-managed keys

  AC-5                                All data in transit uses TLS 1.2 or
                                      higher

  AC-6                                JWT tokens are used for API
                                      authentication with secrets stored
                                      in AWS Secrets Manager, not in
                                      environment variables or source
                                      code

  AC-7                                Spring Boot Security enforces
                                      role-based access on every API
                                      endpoint

  AC-8                                All authentication events and
                                      permission failures are logged to
                                      CloudWatch

  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 🧾 NFR-003 --- Audit Trail and Data Integrity

### Description

For **compliance, accountability, and operational trust**, the system
must maintain a **complete and tamper-evident history** of changes to
all significant records.

Users must **never be able to permanently erase data without explicit
elevated authorization**.

------------------------------------------------------------------------

### Acceptance Criteria

  -----------------------------------------------------------------------
  ID                                  Requirement
  ----------------------------------- -----------------------------------
  AC-1                                All create, update, and delete
                                      operations on contact, business,
                                      opportunity, order, contract, and
                                      ticket records are logged with the
                                      user ID, timestamp, and nature of
                                      the change

  AC-2                                Soft delete is the default delete
                                      behavior --- records are hidden
                                      from standard views but remain in
                                      the database

  AC-3                                Hard delete is restricted to users
                                      with an explicit administrative
                                      role and every hard delete is
                                      logged

  AC-4                                Previous versions of records can be
                                      viewed and rolled back by
                                      authorized users

  AC-5                                The audit log itself is append-only
                                      and cannot be modified or deleted
                                      by any application-level user

  AC-6                                Audit records are retained for a
                                      minimum of seven years in line with
                                      standard business compliance
                                      practice

  -----------------------------------------------------------------------

------------------------------------------------------------------------

# ⚡ NFR-004 --- Scalability and Performance

### Description

MJ Logistics is **growing rapidly with a 42% sales increase over the
past two years**.

The infrastructure must **scale to meet growing user demand and data
volumes without requiring architectural redesign**.\
Performance must remain **consistent as the system grows**.

------------------------------------------------------------------------

### Acceptance Criteria

  -----------------------------------------------------------------------
  ID                                  Requirement
  ----------------------------------- -----------------------------------
  AC-1                                The ECS Fargate service supports
                                      horizontal scaling by increasing
                                      task count without downtime

  AC-2                                RDS is provisioned with the option
                                      to enable Multi-AZ failover and
                                      read replicas as data volumes
                                      increase

  AC-3                                The database schema is designed to
                                      accommodate new fields and
                                      relationships without breaking
                                      existing queries or reports

  AC-4                                API response times for standard
                                      operations remain under 2 seconds
                                      under normal load and under 4
                                      seconds during peak load

  AC-5                                CloudWatch alarms notify the
                                      operations team when CPU, memory,
                                      or response time thresholds are
                                      exceeded

  AC-6                                Infrastructure changes to scale up
                                      or out are handled entirely through
                                      Terraform with no manual AWS
                                      console intervention

  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 🟢 NFR-005 --- Availability and Disaster Recovery

### Description

The CRM is a **business-critical system** that sales and support teams
depend on throughout the working day.

Unplanned downtime **directly impacts revenue and customer
relationships**.\
The system must be designed for **high availability with a clear
recovery process** if an incident occurs.

------------------------------------------------------------------------

### Acceptance Criteria

  -----------------------------------------------------------------------
  ID                                  Requirement
  ----------------------------------- -----------------------------------
  AC-1                                The production environment targets
                                      99.9% uptime during business hours

  AC-2                                The ECS service is deployed across
                                      multiple Availability Zones in
                                      production

  AC-3                                ALB health checks automatically
                                      route traffic away from unhealthy
                                      ECS tasks

  AC-4                                RDS automated backups run daily
                                      with a retention period of at least
                                      7 days

  AC-5                                A recovery runbook documents the
                                      steps to restore service in the
                                      event of a failure

  AC-6                                A staging environment exists where
                                      infrastructure changes and
                                      application updates can be tested
                                      before reaching production

  AC-7                                Blue/green or rolling deployment
                                      strategies are used to deploy
                                      updates without service
                                      interruption

  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 🧩 NFR-006 --- Maintainability and Extensibility

### Description

The system will **evolve over time as MJ Logistics grows and business
requirements change**.

The architecture must make it **straightforward for future engineers to
understand, modify, and extend the system** without needing to
reverse-engineer undocumented decisions.

------------------------------------------------------------------------

### Acceptance Criteria

  -----------------------------------------------------------------------
  ID                                  Requirement
  ----------------------------------- -----------------------------------
  AC-1                                All infrastructure is defined as
                                      code in Terraform with no manually
                                      provisioned resources in production

  AC-2                                Architecture Decision Records
                                      (ADRs) document the reasoning
                                      behind all significant technical
                                      choices

  AC-3                                The Angular frontend uses a modular
                                      feature-based structure so new CRM
                                      modules can be added without
                                      touching existing ones

  AC-4                                The Spring Boot backend follows a
                                      layered architecture (controller →
                                      service → repository) with clear
                                      separation of concerns

  AC-5                                All public API endpoints are
                                      documented

  AC-6                                The codebase maintains a minimum of
                                      70% unit test coverage on business
                                      logic

  AC-7                                New developers can run the full
                                      application locally using a single
                                      `docker compose up` command with no
                                      additional setup steps

  -----------------------------------------------------------------------
