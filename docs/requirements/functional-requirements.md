# ⚙️ Functional Requirements

> **Source:** *Interpreted from the MJ Logistics Gaming Company CRM
> Requirements document*\
> These requirements define **specific behaviors and functions the
> system must perform.**

------------------------------------------------------------------------

# 📊 Requirements Overview

  ID           Requirement                              Domain
  ------------ ---------------------------------------- ------------------
  **FR-001**   Contact and Business Entity Management   CRM Core
  **FR-002**   Ticketing System and Workflow            Support
  **FR-003**   Opportunity and Pipeline Management      Sales
  **FR-004**   Quoting and Order Management             Sales Operations
  **FR-005**   Contract Management                      Legal / Sales
  **FR-006**   Forecasting                              Analytics

------------------------------------------------------------------------

# 🧩 FR-001 --- Contact and Business Entity Management

### Description

The system must allow users to **create, read, update, and manage
contact and business records**. Businesses are the **top-level entity**,
with contacts linked beneath them.

The system must handle the complexity of contacts **moving between
businesses, holding multiple roles, and being associated with
sub-companies or regional offices.**

------------------------------------------------------------------------

### Acceptance Criteria

  -----------------------------------------------------------------------
  ID                                  Requirement
  ----------------------------------- -----------------------------------
  AC-1                                Users can create a business entity
                                      with name, address, phone numbers,
                                      and custom fields

  AC-2                                Duplicate detection runs
                                      automatically when a new business
                                      is entered and alerts the user to
                                      potential matches

  AC-3                                Contacts can be linked to one or
                                      more businesses and assigned one or
                                      more roles

  AC-4                                A contact's history is preserved
                                      when they move to a new business or
                                      change roles

  AC-5                                Partial entries are saved and
                                      flagged with a visual indicator for
                                      follow-up completion

  AC-6                                During an active call, a user can
                                      tag the interaction to an existing
                                      contact or create a new one without
                                      leaving the call log screen

  AC-7                                Contacts are categorized by type
                                      and the category is visible and
                                      filterable across the system
                                      
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 🎫 FR-002 --- Ticketing System and Workflow

### Description

Every **inbound and outbound communication** with a contact must be
captured as a ticket.

The ticketing system manages the **full lifecycle of an interaction from
first contact through resolution**, ensuring nothing is lost and all
follow-ups are tracked.

------------------------------------------------------------------------

### Acceptance Criteria

  -----------------------------------------------------------------------
  ID                                  Requirement
  ----------------------------------- -----------------------------------
  AC-1                                A ticket is created for every new
                                      communication or inquiry and linked
                                      to the relevant contact and
                                      business

  AC-2                                Each ticket records the contact
                                      name, reason for contact, date,
                                      time, assigned user, and current
                                      status

  AC-3                                All email replies related to a
                                      ticket are automatically captured
                                      and appended to that ticket's
                                      thread

  AC-4                                Tickets have a defined workflow
                                      with stages such as Open, In
                                      Progress, Pending, and Resolved

  AC-5                                An audit trail records every status
                                      change, note addition, and user
                                      action on each ticket

  AC-6                                Tickets can be escalated,
                                      reassigned, or linked to other
                                      tickets where interactions are
                                      related

  AC-7                                No two tickets share the same
                                      identifier --- each is uniquely
                                      referenced in the system

  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 📈 FR-003 --- Opportunity and Pipeline Management

### Description

The sales team needs structured tools to **manage sales opportunities
from first identification through to close**.

The system must support **pipeline tracking, competitive analysis, and
workflow-driven progression through sales stages.**

------------------------------------------------------------------------

### Acceptance Criteria

  -----------------------------------------------------------------------
  ID                                  Requirement
  ----------------------------------- -----------------------------------
  AC-1                                Opportunities are created and
                                      linked to a contact and business
                                      record

  AC-2                                Each opportunity progresses through
                                      configurable pipeline stages with
                                      required fields at each stage

  AC-3                                Win and loss outcomes are recorded
                                      with reasons, competitor details,
                                      and product comparisons

  AC-4                                Discount requests trigger an
                                      approval workflow before being
                                      applied to a quote

  AC-5                                The sales pipeline is visible as a
                                      dashboard view filterable by stage,
                                      owner, product, and time period

  AC-6                                Activity history and all
                                      communications are visible directly
                                      from the opportunity record

  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 💰 FR-004 --- Quoting and Order Management

### Description

The system must support the **commercial transaction process from
generating a quote through fulfilling an order**.

This includes **pricing configuration, electronic approval, and
converting a confirmed quote into an active order.**

------------------------------------------------------------------------

### Acceptance Criteria

  -----------------------------------------------------------------------
  ID                                  Requirement
  ----------------------------------- -----------------------------------
  AC-1                                Quotes are generated within the
                                      system and include product
                                      selection, pricing, discounts, tax,
                                      freight, and currency

  AC-2                                A price catalog is maintained
                                      within the system and applied
                                      automatically when products are
                                      added to a quote

  AC-3                                Quotes support electronic
                                      signatures for approval

  AC-4                                A confirmed quote is converted to
                                      an order in a single action without
                                      re-entering data

  AC-5                                Orders support reordering, partial
                                      ordering, and real-time inventory
                                      and availability checks

  AC-6                                A customer self-service portal
                                      allows contacts to view and manage
                                      their own orders

  AC-7                                Order and quote records are
                                      version-controlled with a full
                                      change history

  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 📜 FR-005 --- Contract Management

### Description

Every completed deal requires a **contract**.

The system must manage the **full contract lifecycle including creation,
review, approval, signing, and ongoing term tracking** to ensure
compliance and timely renewal or termination.

------------------------------------------------------------------------

### Acceptance Criteria

  -----------------------------------------------------------------------
  ID                                  Requirement
  ----------------------------------- -----------------------------------
  AC-1                                Contracts are created from within
                                      the system and linked to the
                                      relevant opportunity and business

  AC-2                                An approval and authorization
                                      workflow governs the contract
                                      review process before signing

  AC-3                                Electronic signing is supported
                                      within the system

  AC-4                                Contract terms, start dates, end
                                      dates, and renewal windows are
                                      tracked and surfaced to relevant
                                      users

  AC-5                                Automated alerts notify assigned
                                      users when a contract is
                                      approaching renewal or termination

  AC-6                                Terminated or expired contracts are
                                      retained in the system as
                                      historical records and are not
                                      deleted


  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 📊 FR-006 --- Forecasting

### Description

Sales managers need the ability to **predict future revenue based on
pipeline data and historical performance**.

Forecasting must support **multiple views, manager adjustments, and
product-level breakdowns** to give leadership an accurate picture of
expected business performance.

------------------------------------------------------------------------

### Acceptance Criteria

  -----------------------------------------------------------------------
  ID                                  Requirement
  ----------------------------------- -----------------------------------
  AC-1                                Forecasts are generated
                                      automatically based on current
                                      pipeline data and historical close
                                      rates

  AC-2                                Managers can manually adjust
                                      forecast figures and record the
                                      reason for the adjustment

  AC-3                                Forecasts support multiple periods
                                      --- weekly, monthly, quarterly, and
                                      annually

  AC-4                                Baseline snapshots can be taken and
                                      compared against later forecasts to
                                      measure accuracy

  AC-5                                Product-level forecasting shows
                                      expected revenue broken down by
                                      product line

  AC-6                                Currency adjustments are applied
                                      automatically for any deals
                                      involving foreign currency

  AC-7                                Machine-assisted forecasting
                                      provides a model-generated
                                      prediction alongside the manager's
                                      view


  -----------------------------------------------------------------------
