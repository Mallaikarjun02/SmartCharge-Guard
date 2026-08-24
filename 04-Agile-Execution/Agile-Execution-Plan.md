# SmartCharge Guard — Agile Execution Planning & Backlog Management

**Project Name:** SmartCharge Guard (OTA EV Charging & Battery Safety Platform)  
**Repository Module:** `04-Agile-Execution/Agile-Execution-Plan.md`  
**Document Version:** 1.0 | **Sprint Cadence:** 2 Weeks | **Framework:** Scrum  

---

## 1. Executive Summary & Agile Governance Framework

This document details the Agile Execution Strategy for SmartCharge Guard, an enterprise-grade OTA-enabled EV charging and thermal management system. Operating within a 2-week Scrum cadence across a cross-functional delivery team, this plan outlines backlog grooming, story estimation, sprint commitment, ceremony structures, and risk management to ensure high-velocity, safety-compliant incremental releases.

### Core Agile Framework Parameters
* **Agile Methodology:** Scrum with Kanban flow elements for emergency hotfixes and firmware patches.
* **Sprint Cycle:** 2-week fixed iterations (10 working days).
* **Cross-Functional Team Structure:** 1 Product Owner (PO), 1 Scrum Master (SM), 3 Backend/Telemetry Engineers, 2 Embedded/IoT Firmware Engineers, 1 Mobile/UX Engineer, 1 QA/Automation Engineer (Total: 9 FTE).
* **Sprint Velocity Baseline:** 42 Story Points (SP) per sprint based on historic velocity calculations.

---

## 2. Product Backlog & Prioritized User Stories

The product backlog is organized into high-impact Epics and actionable User Stories[cite: 2]. Stories are prioritized using MoSCoW and estimated using Fibonacci Story Points (1, 2, 3, 5, 8, 13) during Backlog Refinement[cite: 2].

| Story ID | Epic / Module | User Story Statement | Acceptance Criteria (Gherkin / Functional) | SP | Priority | Target Sprint |
| :--- | :--- | :--- | :--- | :---: | :---: | :---: |
| **US-101** | Thermal Safety | As a Fleet Driver, I want charging to automatically slow down when battery temp >45°C so that thermal runaway is prevented. | GIVEN battery temp reaches 45°C, WHEN DC fast charging is active, THEN scale current down by 30% within 500ms and display 'Thermal Protection Active' on app. | 8 | Must-Have | Sprint 1 |
| **US-102** | Telemetry Ingestion | As a Platform Lead, I want an MQTT telemetry handler so that BMS voltage and temp data are logged at 1Hz. | GIVEN active charging session, WHEN BMS emits MQTT payload, THEN parse and store cell voltage, current, and pack temp in Redis within <50ms latency. | 5 | Must-Have | Sprint 1 |
| **US-103** | Dynamic ETA | As an EV Driver, I want an updated charging ETA on my phone so I can plan my route accurately during thermal throttling. | GIVEN charging rate is throttled, WHEN dynamic ETA model calculates revised charge time, THEN refresh mobile app ETA value within 2 seconds. | 5 | Must-Have | Sprint 1 |
| **US-104** | ToU Optimization | As a Fleet Manager, I want to schedule charging during off-peak hours so that energy grid costs are reduced by 15%. | GIVEN utility tariff schedule, WHEN vehicle is plugged in during peak hours, THEN delay fast charging until off-peak window unless override is tapped. | 8 | Must-Have | Sprint 2 |
| **US-105** | Canary OTA Pipeline | As an Embedded Systems Lead, I want a staged OTA deployment pipeline so firmware updates roll out safely without bricking units. | GIVEN new firmware build v2.1, WHEN OTA rollout initiates, THEN deploy to 1% canary group first; auto-rollback if error rate exceeds 0.05% within 1 hour. | 8 | Should-Have | Sprint 2 |
| **US-106** | Fleet Operations UI | As a Depot Manager, I want a live web dashboard showing active station draw and battery temperatures. | GIVEN 50+ connected chargers, WHEN viewing depot dashboard, THEN show real-time thermal status heatmaps updating every 3 seconds. | 5 | Should-Have | Sprint 2 |
| **US-107** | Predictive Pre-Cooling | As a Driver, I want my battery pre-conditioned before arrival at a fast charger so charging starts at optimal speed. | GIVEN navigation destination set to DC charger, WHEN vehicle is 10 min away, THEN initiate thermal management loop to cool pack to 25°C. | 13 | Could-Have | Sprint 3 |

---

## 3. Sprint Planning & Incremental Execution Strategy

### Sprint 1 Execution Plan (Capacity: 42 Story Points)
* **Sprint Goal:** Deliver MVP Thermal Safety Cutoff Engine and Real-Time BMS Telemetry Ingestion with dynamic driver notifications[cite: 2].
* **Included Stories:** US-101 (8 SP), US-102 (5 SP), US-103 (5 SP), Tech Spike: Hardware Safety Bus Latency Testing (3 SP), QA Automation Suite Setup (5 SP)[cite: 2]. Total Allocated: 26 SP (Core MVP Focus)[cite: 2].

### Definition of Done (DoD) Checklist
* Code peer-reviewed and approved by at least 2 senior developers[cite: 2].
* Unit test coverage >85% across all new telemetry ingestion microservices[cite: 2].
* Integration tests passing on hardware-in-the-loop (HIL) test bench for thermal throttling[cite: 2].
* Security audit completed for MQTT payloads and mobile API endpoints[cite: 2].
* Documentation updated in repository (`/04-Agile-Execution` and OpenAPI specs)[cite: 2].

---

## 4. Agile Ceremonies & Operational Cadence

To maintain alignment, continuous delivery, and rapid feedback loops, the team executes five core Scrum ceremonies[cite: 2]:

| Ceremony | Frequency / Timing | Duration | Key Participants | Primary Objective & Output |
| :--- | :--- | :--- | :--- | :--- |
| **Sprint Planning** | First Monday of Sprint (9:00 AM) | 2 Hours | PO, SM, Dev Team | Select prioritized backlog items, finalize Sprint Goal, commit to Sprint Backlog. |
| **Daily Stand-up** | Mon-Fri (9:30 AM) | 15 Mins | Dev Team, SM, PO | Identify blockers, track sprint progress against burndown chart using 3 key questions. |
| **Backlog Grooming** | Second Wednesday (2:00 PM) | 1.5 Hours | PO, SM, Dev Team | Refine user stories, break down epics, update acceptance criteria, assign Fibonacci story points. |
| **Sprint Review & Demo** | Final Friday (3:00 PM) | 1 Hour | PO, SM, Dev Team, Stakeholders | Demonstrate working software increments on HIL bench; gather stakeholder feedback. |
| **Retrospective** | Final Friday (4:15 PM) | 45 Mins | PO, SM, Dev Team | Inspect sprint performance (What went well? What didn't? Action items for improvement). |

---

## 5. Process Visualization & Workflows

### Agile Lifecycle & Ceremony Workflow
```text
+-----------------------------------------------------------------------------------+
|                             PRODUCT BACKLOG (PO Managed)                         |
+-----------------------------------------------------------------------------------+
                                          |
                                          v  [Backlog Grooming & Refinement]
+-----------------------------------------------------------------------------------+
|                            SPRINT PLANNING (Commit 42 SP)                         |
+-----------------------------------------------------------------------------------+
                                          |
      +-----------------------------------+-----------------------------------+
      |                                                                       |
      v                                                                       v
+---------------------------+                             +---------------------------+
|  DAILY STAND-UP (15 Min)  | <--- [2-Week Sprint Loop] ---| KANBAN DEVELOPMENT BOARD  |
|  - What was done?         |                             | To Do -> In Prog -> Code  |
|  - What will be done?     |                             | Review -> HIL QA -> Done  |
|  - Any Blockers?          |                             |                           |
+---------------------------+                             +---------------------------+
                                          |
                                          v
+-----------------------------------------------------------------------------------+
|                        SPRINT REVIEW & DEMO (Working Increment)                   |
+-----------------------------------------------------------------------------------+
                                          |
                                          v
+-----------------------------------------------------------------------------------+
|                        RETROSPECTIVE (Continuous Improvement)                     |
+-----------------------------------------------------------------------------------+
Kanban Board Column Workflow & WIP LimitsBacklog (No Limit)To Do (Max 10)In Development (Max 6)Code Review / PR (Max 4)HIL QA Testing (Max 3)Done (Increment)Prioritized stories ready for sprint ingestion.Committed stories for active sprint.Actively being coded by dev team.Peer review and security scan in progress.Hardware-in-the-loop validation.Meets Definition of Done (DoD).
Identified Risk,Impact,Likelihood,Category,Agile Mitigation Strategy & Contingency
HIL Hardware Bench Bottlenecks,High,High,Infrastructure,Implement mock BMS software simulators for dev local testing; reserve physical HIL bench strictly for nightly automated builds.
Scope Creep during Mid-Sprint,High,Medium,Process,Enforce strict PO gatekeeping. Any new emergency requirement requires dropping an equivalent SP item from the current sprint.
Firmware Canary Deployment Failures,Critical,Low,Technical / Safety,"Automate dual-bank memory rollback on IoT controller. If error telemetry spikes >0.05%, execute instant automatic OTA rollback."
Team Velocity Drops due to Blocker,Medium,Medium,People / Resources,Swarm team resources on blocked stories during Daily Standup; cross-train developers in embedded telemetry parsing.
