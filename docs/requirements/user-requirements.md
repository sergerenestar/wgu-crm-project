# 👥 User Requirements

> **Source:** *Interpreted from the MJ Logistics Gaming Company CRM
> Requirements document*\
> These requirements define **what the system's users need to be able to
> do and the conditions under which they will use it.**

------------------------------------------------------------------------

# 📊 Requirements Overview

  -----------------------------------------------------------------------
  ID                      Requirement             Domain
  ----------------------- ----------------------- -----------------------
  **UR-001**              Role-Based Access       Security
                          Control                 

  **UR-002**              Cross-Platform and      Platform
                          Browser Compatibility   

  **UR-003**              Contact Preference and  CRM Core
                          Self-Service Management 

  **UR-004**              Concurrent User         Performance
                          Performance             

  **UR-005**              Intuitive User          UX
                          Interface and Usability

 **UR-006**              Active Directory        Authentication
                          Integration             
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 🔐 UR-001 --- Role-Based Access Control

### Description

The CRM will be used by a wide range of employees across different
departments including **sales, management, support, and
administration**.

Each user type has a different scope of responsibility and must only be
able to access data and features that are relevant to their role. Access
must be controlled centrally and enforced consistently across the entire
system.

------------------------------------------------------------------------

### Acceptance Criteria

  -----------------------------------------------------------------------
  ID                                  Requirement
  ----------------------------------- -----------------------------------
  AC-1                                Every user is assigned one or more
                                      roles that determine what features
                                      and data they can access

  AC-2                                Role permissions are managed by
                                      administrators without requiring
                                      code changes

  AC-3                                Users cannot view, edit, or delete
                                      data outside their permitted scope

  AC-4                                Hard delete functionality is
                                      restricted to specific elevated
                                      roles only

  AC-5                                Soft delete is available to
                                      standard roles --- data is hidden
                                      from view but retained in the
                                      database

  AC-6                                Permission changes take effect
                                      immediately without requiring a
                                      user to log out
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 🌐 UR-002 --- Cross-Platform and Browser Compatibility

### Description

MJ Logistics has employees working from multiple locations using a
variety of **devices, operating systems, and browsers**.\
The system must be fully functional across all supported platforms
without degradation in experience or functionality.

------------------------------------------------------------------------

### Acceptance Criteria

  -----------------------------------------------------------------------
  ID                                  Requirement
  ----------------------------------- -----------------------------------
  AC-1                                The Angular frontend renders and
                                      functions correctly on the latest
                                      versions of Chrome, Chromium,
                                      Firefox, Microsoft Edge, and Safari

  AC-2                                The system is fully usable on the
                                      latest versions of Windows, iOS,
                                      and Android operating systems

  AC-3                                The interface is responsive and
                                      supports tablet and mobile devices

  AC-4                                No platform-specific features are
                                      required to access core CRM
                                      functionality

  AC-5                                Users on mobile devices can log
                                      activity, view contacts, and manage
                                      tickets without needing a desktop
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 📞 UR-003 --- Contact Preference and Self-Service Management

### Description

Users of the CRM --- both **internal staff and business contacts** ---
must be able to manage how they are contacted.

Contacts must be able to set and update their **communication
preferences**, and internal users must be able to view and respect those
preferences during interactions.

------------------------------------------------------------------------

### Acceptance Criteria

  -----------------------------------------------------------------------
  ID                                  Requirement
  ----------------------------------- -----------------------------------
  AC-1                                Contacts can set marketing and
                                      communication preferences at the
                                      time of registration and update
                                      them at any time

  AC-2                                Internal users can view a contact's
                                      current communication preferences
                                      before initiating outreach

  AC-3                                The system enforces communication
                                      rules and flags any action that
                                      would violate a contact's
                                      preferences

  AC-4                                Different preference rules apply to
                                      business contacts versus end-user
                                      contacts

  AC-5                                Preference changes are logged with
                                      a timestamp for compliance and
                                      audit purposes
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# ⚡ UR-004 --- Concurrent User Performance

### Description

With **2,000 total users** and up to **500 expected to use the system
simultaneously during peak periods**, the CRM must maintain consistent
performance under load.

Users should not experience slowdowns, timeouts, or errors during normal
peak usage.

------------------------------------------------------------------------

### Acceptance Criteria

  -----------------------------------------------------------------------
  ID                                  Requirement
  ----------------------------------- -----------------------------------
  AC-1                                The system supports a minimum of
                                      500 concurrent active users without
                                      performance degradation

  AC-2                                Page load and API response times
                                      remain within acceptable thresholds
                                      under peak load (target: under 2
                                      seconds for standard operations)

  AC-3                                The underlying infrastructure
                                      scales to accommodate user growth
                                      beyond current numbers

  AC-4                                Performance is monitored via
                                      CloudWatch with alerts triggered if
                                      thresholds are breached

  AC-5                                Load testing is conducted before
                                      production deployment to validate
                                      concurrency requirements
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 🧭 UR-005 --- Intuitive User Interface and Usability

### Description

The CRM will be used daily by employees across different **technical
skill levels**.

The interface must be **clean, consistent, and easy to learn**. Users
should be able to complete common tasks such as logging a call, creating
a contact, or raising a ticket **without requiring training
documentation**.

------------------------------------------------------------------------

### Acceptance Criteria

  -----------------------------------------------------------------------
  ID                                  Requirement
  ----------------------------------- -----------------------------------
  AC-1                                Core workflows such as contact
                                      creation, activity logging, and
                                      ticket submission require no more
                                      than 3--5 steps

  AC-2                                Navigation is consistent across all
                                      modules with a clear menu structure

  AC-3                                Form validation provides helpful,
                                      specific error messages that guide
                                      the user to correct input

  AC-4                                Partial data entries are accepted
                                      and flagged for completion rather
                                      than rejected outright

  AC-5                                The interface uses consistent
                                      terminology aligned with MJ
                                      Logistics business language

  AC-6                                New users can complete basic tasks
                                      without requiring system
                                      administrator assistance
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 🔑 UR-006 --- Active Directory Integration

### Description

MJ Logistics employees already have company credentials managed through
**Active Directory**.

Users should not need to maintain a separate set of credentials for the
CRM. The system must integrate with the company's existing **Active
Directory server for authentication**.

------------------------------------------------------------------------

### Acceptance Criteria

  -----------------------------------------------------------------------
  ID                                  Requirement
  ----------------------------------- -----------------------------------
  AC-1                                Users log in to the CRM using their
                                      existing company Active Directory
                                      credentials

  AC-2                                User provisioning and deactivation
                                      in Active Directory is reflected in
                                      CRM access automatically

  AC-3                                Single Sign-On (SSO) is supported
                                      so users already authenticated on
                                      the company network are not
                                      prompted to log in again

  AC-4                                Failed login attempts are logged
                                      and accounts can be locked after a
                                      defined number of failures

  AC-5                                Password management remains with
                                      Active Directory and is not handled
                                      by the CRM
  -----------------------------------------------------------------------
