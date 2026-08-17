# Operations Maintenance Process Automation & Tracking System
## Project Overview
Maintenance operations often generate large volumes of information across forms, spreadsheets, messaging platforms, field records, and email. When these processes depend heavily on manual communication and reporting, important notifications can be delayed, maintenance activities can be overlooked, and answering basic operational questions can consume unnecessary time.

This project was developed to address that problem.

The Operations Maintenance Process Automation & Tracking System is an end-to-end workflow designed to improve how preventive and corrective maintenance activities are captured, communicated, monitored, and reported.

The system combines:

* Structured maintenance data collection
* Automated preventive maintenance notifications
* Immediate corrective maintenance notifications
* Centralized maintenance tracking
* Maintenance status monitoring
* Operational dashboards
* Due and overdue maintenance visibility
* Automated weekly reporting

The objective was not simply to automate individual tasks, but to create a more reliable operational workflow where maintenance information moves from field submission to communication, tracking, monitoring, and reporting with minimal manual intervention.

---
## The Problem

Before the system was introduced, maintenance coordination relied heavily on manual processes.

###  1. Maintenance notifications were fragmented

Maintenance information was often communicated through WhatsApp groups and informal messages.

This created several problems:

* Important notifications could be missed
* Communication was difficult to track
* Different teams had different levels of visibility
* Urgent service disruptions required faster escalation
* There was no consistent notification workflow

For corrective maintenance, a delay in communication could also affect customer experience. For example, an inverter failure or other service-disrupting issue may require the Customer Experience team to communicate with affected customers while the technical issue is being resolved.

### 2. Preventive maintenance required reliable scheduling

Preventive maintenance is planned in advance, meaning the maintenance record should be submitted before the actual maintenance date.

However, this created another risk: a maintenance activity could be documented but the notification could still be forgotten or sent late.

### 3. Operational questions required manual data preparation

Questions such as:

* How many sites were completed this month?
* How many sites are due next month?
* Which sites are overdue?
* How many maintenance activities were completed this week?
* How many issues remain pending?

required manually filtering, sorting, calculating, and reorganizing spreadsheet data.

This was repetitive, time-consuming, and unnecessarily dependent on manual spreadsheet manipulation.

### 4. Weekly reporting was also manual

Maintenance records uploaded from field data collection systems had to be audited and then manually filtered to extract the information required for weekly reporting.

The process consumed time that could otherwise be used for operational analysis, follow-up, and coordination.

---
## The Solution

I designed a centralized maintenance workflow that connects data capture, communication, tracking, monitoring, and reporting.

Instead of treating maintenance notifications, tracking, dashboards, and reports as separate activities, the system connects them into one operational process.

### Core workflow

```text
                                                Maintenance Activity
                                                        │
                                                        ▼
                                                Structured Form Submission
                                                        │
                                                        ├───────────────┐
                                                        │               │
                                                        ▼               ▼
                                                Corrective          Preventive
                                                Maintenance        Maintenance
                                                        │               │
                                                        ▼               ▼
                                                Immediate          Scheduled
                                                Notification       Daily Notification
                                                        │               │
                                                        └───────┬───────┘
                                                                ▼
                                                        Central Maintenance
                                                             Tracker
                                                                │
                                                                ▼
                                                       Status & Due Monitoring
                                                                │
                                                                ▼
                                                           Dashboard
                                                                │
                                                                ▼
                                                       Weekly Maintenance
                                                             Reporting
```

This creates a single operational flow from maintenance initiation to management reporting.

---

## Key Components

### 1. Structured Maintenance Forms

Two separate forms were created to capture maintenance activities according to their operational nature.

#### Preventive Maintenance Form

Used for planned maintenance activities.

Because preventive maintenance is scheduled in advance, submissions can be made before the maintenance date.

#### Corrective Maintenance Form

Used for unplanned or urgent maintenance activities.

Corrective maintenance can involve issues such as equipment failure or service disruption and therefore requires immediate communication.

Separating the two workflows allowed each type of maintenance to have an appropriate notification strategy.

### 2. Automated Corrective Maintenance Notification

Corrective maintenance uses an immediate notification workflow.

#### Trigger

**On form submission**

Once a corrective maintenance form is submitted:

```text
                                                Corrective Maintenance Form
                                                             ↓
                                                      Form Submission
                                                             ↓
                                                      Automation Trigger
                                                             ↓
                                                      Notification Email
                                                             ↓
                                                     Relevant Team Members
```

This design was intentional.

Corrective maintenance can represent an active operational problem. For example, an inverter failure may affect service availability and require the technical team to respond while the Customer Experience team manages customer communication.

The objective is therefore to minimize the time between issue identification and stakeholder awareness.

### 3. Automated Preventive Maintenance Notification

Preventive maintenance follows a different notification model because it is planned.

The system automatically checks maintenance activities scheduled for the current day during a defined period.

#### Automated workflow

```text
                                                  Maintenance records
                                                          ↓
                                                  Check today's maintenance
                                                          ↓
                                                  7:00 AM – 8:00 AM
                                                          ↓
                                                  Send notification
                                                          ↓
                                                  Update notification status
                                                          ↓
                                                        "Sent"
```

The notification status prevents the same maintenance activity from being automatically notified again.

#### Why this approach?

The maintenance record should normally exist before the maintenance date.

Therefore, the system uses the scheduled maintenance date as the basis for daily notification.

This reduces the risk of:

* Forgotten notifications
* Late notifications
* Missed planned maintenance
* Repeated notifications

#### Exception handling

If a maintenance activity for the current day is submitted after the automated notification window, the notification can be triggered manually by changing the notification status to "Send".

Once the notification is successfully sent, the status changes to "Sent"

This creates a simple control mechanism:

```text
                                        Send → Notification triggered → Sent
```

### 4. Centralized Maintenance Tracking

The notification system solved the communication problem, but another challenge remained:

> **How do we know what is happening across all maintenance activities?**

A centralized maintenance tracker was therefore developed.

The tracker provides visibility into:

* Maintenance history
* Planned maintenance
* Corrective maintenance
* Maintenance dates
* Assigned engineers
* Site information
* Pending issues
* Completion status
* Notification status
* Maintenance due dates

Thus turning individual maintenance records into an operational monitoring system.

### 5. Maintenance Dashboard

As maintenance records accumulated, another operational need became clear.

Management frequently needed quick answers to questions such as:


How many sites have been completed this month?

What is due next month?

Which sites are overdue?

How many maintenance issues are still pending?


Instead of repeatedly filtering and manipulating the underlying spreadsheet, I developed a maintenance dashboard that provides these answers at a glance.

#### Key KPIs

The dashboard provides visibility into:

* Total Sites
* Sites Due This Month
* Sites Due Next Month
* Sites Completed This Month
* Pending Issues
* Sites Completed This Week
* Sites Completed Last Week

This changes the spreadsheet from a passive record of maintenance activities into an operational decision-support tool.

### 6. Due Maintenance Monitoring

The dashboard provides a detailed view of sites due for maintenance during the current month.

The view includes:

| Field                     | Purpose                                                       |
| ------------------------- | ------------------------------------------------------------- |
| Site Name                 | Identifies the maintenance location                           |
| Group                     | Shows the responsible operational group                       |
| Assigned Engineer         | Identifies ownership                                          |
| Last Maintenance Date     | Shows the previous maintenance activity                       |
| Next Maintenance Date     | Shows when maintenance is due                                 |
| Days Remaining            | Indicates urgency                                             |
| Current Status            | Shows whether the activity is overdue, due today, or due soon |

This allows the team to identify upcoming maintenance activities without manually searching through the entire tracker.

### 7. Next-Month Maintenance Visibility

The dashboard also provides a forward-looking view of sites scheduled for maintenance in the following month.

This supports early planning by showing:

* Site
* NOC
* Assigned engineer
* Last maintenance date
* Next maintenance date
* Days remaining

The objective is to move maintenance management from reactive tracking to proactive planning.

### 8. Overdue Maintenance Monitoring

Overdue maintenance receives a dedicated view.

The dashboard identifies sites where the next maintenance date has already passed and displays the number of days overdue.

For example:

```text
Next Maintenance Date: 10 Aug
Current Date:          17 Aug
Days Remaining:        -7
```

A negative value immediately communicates that follow-up is required.

This provides a simple way to prioritize overdue maintenance activities.

### 9. Automated Weekly Reporting

The maintenance workflow was extended beyond tracking and dashboarding to address weekly reporting.

Previously, after auditing maintenance records collected through the field reporting process, the required reporting fields had to be manually filtered and prepared.

The improved workflow separates data auditing from report preparation.

#### New workflow

```text
                                                                                  Maintenance Records
                                                                                          ↓
                                                                                  Audit Master Records
                                                                                          ↓
                                                                                  Approved / Validated Data
                                                                                          ↓
                                                                                  Automated Reporting View
                                                                                          ↓
                                                                                  Current Reporting Week
                                                                                          ↓
                                                                                  4:00 PM – 5:00 PM Monday
                                                                                          ↓
                                                                                  Automated Email
                                                                                          ↓
                                                                                      Management
```

The reporting view automatically extracts the required fields and reporting period.

The weekly email is then automatically sent during the defined reporting window.

This allows the audit process to remain the main human-controlled activity while repetitive report preparation and distribution are automated.

---

## End-to-End System Architecture

The complete system can be viewed as five connected layers:

```text
                                                                                ┌─────────────────────────────────────┐
                                                                                │         1. DATA CAPTURE             │
                                                                                │  Preventive & Corrective Forms      │
                                                                                └──────────────────┬──────────────────┘
                                                                                                   ↓
                                                                                ┌─────────────────────────────────────┐
                                                                                │       2. COMMUNICATION              │
                                                                                │ Immediate CM notifications          │
                                                                                │ Scheduled PM notifications          │
                                                                                └──────────────────┬──────────────────┘
                                                                                                   ↓
                                                                                ┌─────────────────────────────────────┐
                                                                                │        3. TRACKING                  │
                                                                                │ Central maintenance records         │
                                                                                │ Status & notification controls      │
                                                                                └──────────────────┬──────────────────┘
                                                                                                   ↓
                                                                                ┌─────────────────────────────────────┐
                                                                                │        4. VISIBILITY                │
                                                                                │ KPIs • Due • Overdue • Pending      │
                                                                                │ Maintenance dashboard               │
                                                                                └──────────────────┬──────────────────┘
                                                                                                   ↓
                                                                                ┌─────────────────────────────────────┐
                                                                                │        5. REPORTING                 │
                                                                                │ Automated weekly report generation  │
                                                                                │ and distribution                    │
                                                                                └─────────────────────────────────────┘
```

The result is a connected operational workflow rather than a collection of independent spreadsheets.

---

## Operational Benefits

The system was designed around four major outcomes:

### 1. Faster communication

Corrective maintenance notifications are triggered immediately after submission, reducing the communication gap between issue identification and stakeholder awareness.

### 2. Reduced manual work

Recurring notification, filtering, dashboard preparation, and weekly report distribution activities are automated.

### 3. Improved operational visibility

The dashboard provides a single view of maintenance performance, upcoming activities, overdue sites, and pending issues.

### 4. Better process control

Notification status tracking, structured forms, scheduled automation, and centralized records reduce the risk of missed, duplicated, or poorly documented activities.

---

# From Manual Work to Operational System

The transformation can be summarized as:

| Before                                            | After                                |
| ------------------------------------------------- | ------------------------------------ |
| WhatsApp-based maintenance communication          | Structured notification workflow     |
| Manual corrective notifications                   | Immediate automated notifications    |
| Planned maintenance notifications could be missed | Scheduled daily notification process |
| Manual filtering for operational questions        | Dashboard-driven visibility          |
| Manual due/overdue identification                 | Automated status monitoring          |
| Manual weekly report preparation                  | Automated reporting view             |
| Manual report distribution                        | Scheduled email distribution         |
| Information spread across processes               | Connected maintenance workflow       |

The key improvement was not simply automation.

It was the creation of a **repeatable operational system with clear controls, visibility, and accountability.**

---

# Technologies & Tools

The implementation demonstrates practical use of:

* Google Forms
* Google Sheets
* Google Apps Script
* Spreadsheet formulas and logic
* Automated email workflows
* Dashboard design
* Data validation and auditing
* Operational reporting
* Process automation

The tools served as the implementation layer; the primary focus was **solving an operational problem through process and system design**.

---

# Project Skills Demonstrated

### Operations

* Preventive maintenance tracking
* Corrective maintenance coordination
* Operational monitoring
* Workflow design
* Process improvement
* Stakeholder communication

### Data & Analytics

* Data organization
* Data validation
* KPI development
* Dashboard design
* Status monitoring
* Operational reporting

### Automation

* Event-based automation
* Scheduled automation
* Notification workflows
* Conditional logic
* Automated reporting
* Exception handling

### Problem Solving

* Process analysis
* Bottleneck identification
* Workflow redesign
* Automation opportunity identification
* Operational decision support

---

# Project Documentation

Detailed documentation is organized into the following sections:

| Document                                                  | Description                                                        |
| --------------------------------------------------------- | ------------------------------------------------------------------ |
| [Problem & Objectives](docs/01-problem-and-objectives.md) | Business problem, objectives, and design goals                     |
| [Process Workflow](docs/02-process-workflow.md)           | End-to-end maintenance workflow                                    |
| [System Design](docs/03-system-design.md)                 | Architecture and relationship between components                   |
| [Automation Logic](docs/04-automation-logic.md)           | Preventive, corrective, and reporting automation                   |
| [Dashboard & KPIs](docs/05-dashboard-and-kpis.md)         | Dashboard structure, calculations, and operational metrics         |
| [Reporting Automation](docs/06-reporting-automation.md)   | Automated reporting workflow                                       |
| [Outcomes & Lessons](docs/07-outcomes-and-lessons.md)     | Operational improvements, lessons learned, and future enhancements |

---

# Repository Structure

```text
operations-maintenance-process-automation/
│
├── README.md
│
├── docs/
│   ├── problem-and-objectives.md
│   ├── process-workflow.md
│   ├── system-design.md
│   ├── automation-logic.md
│   ├── dashboard-and-kpis.md
│   ├── reporting-automation.md
│   └── outcomes-and-lessons.md
│
├── visuals/
│   ├── before-process.png
│   ├── system-overview.png
│   ├── maintenance-form.png
│   ├── maintenance-tracker.png
│   ├── dashboard-overview.png
│   ├── due-maintenance.png
│   ├── overdue-maintenance.png
│   ├── corrective-notification.png
│   ├── preventive-notification.png
│   └── automated-report.png
│
├── automation/
│   ├── preventive-maintenance/
│   ├── corrective-maintenance/
│   └── weekly-reporting/
│
├── data/
│   └── sample-maintenance-data.csv
│
├── dashboard/
│   └── README.md
│
└── reporting/
    └── README.md
```

---

# Data & Confidentiality

This repository is intended to demonstrate the **system design, workflow, automation logic, and operational problem-solving approach**.

Production data, customer information, internal communications, credentials, company-specific confidential information, and other sensitive operational records are not included.

Where examples are required, sanitized or simulated data should be used.

---

# Future Improvements

The current workflow provides a strong foundation for maintenance process automation. Potential future improvements include:

* Integration with a dedicated maintenance management system
* Role-based access and permissions
* Automated escalation for overdue maintenance
* Maintenance performance trend analysis
* Engineer-level performance metrics
* Automated exception alerts
* Historical maintenance analytics
* Integration with Power BI or another BI platform
* Centralized database architecture
* Mobile-first maintenance workflow

---

# Conclusion

This project demonstrates how a recurring operational problem can be transformed into a structured technology-enabled workflow.

The solution connects:

**Data Capture → Communication → Tracking → Monitoring → Reporting**

The result is a maintenance process that is more **visible, organized, timely, consistent, and scalable**, while reducing repetitive administrative work.

More importantly, the project demonstrates a practical approach to process improvement:

> **Identify the operational bottleneck → understand the workflow → redesign the process → automate repeatable tasks → create visibility → measure and improve.**

