# 📌 Business Requirements

> **Source:** *Interpreted from the MJ Logistics Gaming Company CRM
> Requirements document*\
> These requirements define **what the business needs the system to
> achieve**, independent of implementation details.

------------------------------------------------------------------------

# 📊 Requirements Overview

  -----------------------------------------------------------------------
  ID                      Requirement             Domain
  ----------------------- ----------------------- -----------------------
  **BR-001**              Consolidated Contact    CRM Core
                          and Business Management 

  **BR-002**              Sales Tracking and      Sales
                          Pipeline Visibility     

  **BR-003**              Centralized Activity    Communication
                          and Communication       
                          Management              

  **BR-004**              Reporting and Business  Analytics
                          Intelligence            

  **BR-005**              Order and Contract      Sales Operations
                          Lifecycle Management    
                          
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 🧩 BR-001 --- Consolidated Contact and Business Management

### Description

MJ Logistics currently manages customer and partner data across
disconnected spreadsheets and databases spread across multiple offices.
The new CRM must serve as a **single source of truth** for all contact
and business information.

Every stakeholder, partner, distributor, and client record must exist in
**one centralized system accessible to all authorized users regardless
of their location**.

------------------------------------------------------------------------

### Acceptance Criteria

  -----------------------------------------------------------------------
  ID                                  Requirement
  ----------------------------------- -----------------------------------
  AC-1                                All business entities are stored in
                                      a single database with no
                                      duplication of records across
                                      offices or departments

  AC-2                                The system detects and flags
                                      duplicate business entries at the
                                      point of data entry

  AC-3                                Contacts can be linked to one or
                                      more businesses, offices, or
                                      sub-companies

  AC-4                                A contact's role, business
                                      affiliation, or office assignment
                                      can be updated without losing
                                      historical data

  AC-5                                Remote and on-site users access the
                                      same data in real time
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 📈 BR-002 --- Sales Tracking and Pipeline Visibility

### Description

With a **42% increase in sales over the past two years**, the business
needs a structured way to track sales activity, manage pipelines, and
forecast revenue.

Sales teams must be able to move opportunities through a defined
pipeline, record wins and losses, and give managers a clear view of
expected revenue across all periods.

------------------------------------------------------------------------

### Acceptance Criteria

  -----------------------------------------------------------------------
  ID                                  Requirement
  ----------------------------------- -----------------------------------
  AC-1                                Sales opportunities can be created,
                                      updated, and progressed through
                                      defined pipeline stages

  AC-2                                Win and loss outcomes are recorded
                                      with reasons and competitive
                                      context

  AC-3                                Sales forecasts can be generated
                                      per period, per product, and per
                                      sales representative

  AC-4                                Managers can view and adjust
                                      forecasts including currency
                                      adjustments for any international
                                      dealings

  AC-5                                Pipeline data is visible in real
                                      time via dashboards accessible to
                                      relevant roles
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 📞 BR-003 --- Centralized Activity and Communication Management

### Description

All meetings, visits, calls, and interactions with clients and
stakeholders must be logged in the CRM. Currently, activity records are
**scattered and inconsistent**.

The business requires a **complete communication history for every
contact**, ensuring that any team member can continue a relationship
with full context.

------------------------------------------------------------------------

### Acceptance Criteria

  -----------------------------------------------------------------------
  ID                                  Requirement
  ----------------------------------- -----------------------------------
  AC-1                                Every interaction with a contact
                                      --- including calls, emails,
                                      meetings, and visits --- is
                                      recorded against that contact's
                                      profile

  AC-2                                The system integrates with
                                      Microsoft Exchange or Outlook so
                                      calendar events and emails sync
                                      with CRM activity records

  AC-3                                A full audit trail is maintained
                                      for all activity entries showing
                                      who logged the activity and when

  AC-4                                Ticket-based workflows are used to
                                      track inquiries from first contact
                                      through to resolution

  AC-5                                Activity records cannot be
                                      permanently deleted by standard
                                      users
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 📊 BR-004 --- Reporting and Business Intelligence

### Description

Leadership and department managers need access to **both high-level and
detailed reports** to make informed business decisions.

The reporting system must be flexible enough to serve **executive
dashboards as well as operational reporting**, while ensuring each user
sees only the data relevant to their role.

------------------------------------------------------------------------

### Acceptance Criteria

  -----------------------------------------------------------------------
  ID                                  Requirement
  ----------------------------------- -----------------------------------
  AC-1                                Predefined reports are available
                                      for common business needs such as
                                      sales performance, pipeline status,
                                      and activity summaries

  AC-2                                Users can build and save custom
                                      reports using a filtering and query
                                      interface

  AC-3                                Executive-level dashboards provide
                                      summary views of key business
                                      metrics

  AC-4                                Report data can be exported in
                                      standard formats (CSV, PDF)

  AC-5                                Access to report data is restricted
                                      based on the user's department and
                                      role

  AC-6                                Historical data is available for
                                      trend analysis and comparison
                                      across periods
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 📦 BR-005 --- Order and Contract Lifecycle Management

### Description

Every sale at MJ Logistics involves **three stages**:

1.  Quote\
2.  Order\
3.  Contract

These stages are currently handled separately with **no unified
tracking**.

The CRM must manage the **full commercial lifecycle**, from quote
generation through contract signing and order fulfillment, reducing
manual handoffs and errors.

------------------------------------------------------------------------

### Acceptance Criteria

  -----------------------------------------------------------------------
  ID                                  Requirement
  ----------------------------------- -----------------------------------
  AC-1                                Quotes can be generated within the
                                      system including pricing,
                                      discounts, taxes, freight, and
                                      currency

  AC-2                                A quote can be converted to an
                                      order without re-entering data

  AC-3                                Contracts are created, tracked, and
                                      stored against the relevant deal
                                      and contact

  AC-4                                Contract signing, approval, and
                                      term tracking are managed within
                                      the system

  AC-5                                Orders support reordering, part
                                      ordering, and a customer
                                      self-service portal

  AC-6                                All quote, order, and contract
                                      records maintain a version history
                                      with rollback capability
  -----------------------------------------------------------------------
