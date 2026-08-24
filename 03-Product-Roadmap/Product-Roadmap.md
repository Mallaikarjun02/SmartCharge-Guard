# ⚡ Week 3: Product Roadmap Design & Feature Prioritization
> **Product Name:** ChargePulse — Smart EV Charging & Fleet Energy Optimization Platform  
> **Repository Module:** 03-Product-Roadmap/Product-Roadmap.md  

---

## 1. Executive Summary & Strategic Scope

This document establishes the official 18-month product roadmap and feature prioritization framework for **ChargePulse**, an enterprise software platform optimizing electric vehicle (EV) charging infrastructure, battery thermal management, and power grid loads for 2W/3W commercial fleets and Charge Point Operators (CPOs).

### Strategic Objectives Mapping
* **OKR 1 (Market Expansion):** Scalable API integration layer to support 25,000 active endpoints across 3 major EV OEMs by Phase 3.
* **OKR 2 (Battery Protection):** Real-time thermal limit monitoring and adaptive DC charging profiles deployed during MVP, reducing cell degradation by 22%.
* **OKR 3 (Energy Savings):** Automated Time-of-Use (ToU) load shifting built in Phase 2 to cut peak grid energy costs by 15%.
* **OKR 4 (System Reliability):** Staged Over-The-Air (OTA) firmware delivery pipeline with automated canary rollouts and instant rollback (<0.01% failure rate).

---

## 2. Feature Prioritization Framework

ChargePulse evaluates features using a combined **RICE Scoring Method** (Reach, Impact, Confidence, Effort) alongside the **MoSCoW Matrix**.

* **RICE Formula:** `(Reach × Impact × Confidence) / Effort`

| Feature Module | Reach (Qtr) | Impact | Confidence | Effort (PM) | RICE Score | MoSCoW Category | Phase |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Real-time BMS Thermal Telemetry Parsing** | 5,000 | 3.0 | 100% | 2.0 | **7,500** | Must-Have (M) | Phase 1 |
| **OCPP 2.0.1 Open Charge Protocol Engine** | 5,000 | 3.0 | 90% | 2.5 | **5,400** | Must-Have (M) | Phase 1 |
| **Dynamic Charging ETA Calculator** | 5,000 | 2.0 | 90% | 1.5 | **6,000** | Must-Have (M) | Phase 1 |
| **Dynamic Time-of-Use (ToU) Load Shifting** | 18,000 | 3.0 | 90% | 3.0 | **16,200** | Must-Have (M) | Phase 2 |
| **Staged Canary OTA Firmware Pipeline** | 18,000 | 2.0 | 80% | 2.0 | **14,400** | Should-Have (S) | Phase 2 |
| **AI Predictive Battery Pre-Conditioning** | 50,000 | 3.0 | 80% | 4.0 | **30,000** | Should-Have (S) | Phase 3 |
| **Multi-Fleet Telemetry Aggregation API** | 50,000 | 2.0 | 90% | 2.5 | **36,000** | Should-Have (S) | Phase 3 |
| **Automated Carbon Offsetting & Billing** | 110,000 | 1.0 | 70% | 3.0 | **25,666** | Could-Have (C) | Phase 4 |
| **Vehicle-to-Grid (V2G) Bi-directional Export**| 220,000 | 2.0 | 50% | 6.0 | **36,666** | Won't-Have (W)* | Phase 5 |

*\*Won't-Have for initial 12-month scope; scheduled for Year 2 expansion.*

---

## 3. Phased Product Roadmap Breakdown

### Phase 1: MVP Core Infrastructure & Safety Controls (Months 1–3)
* **F1.1 Multi-Protocol Telemetry Pipeline:** Ingestion engine for OCPP 2.0.1 and MQTT supporting voltage, current, SoC, and cell thermal data at 1Hz sampling frequency.
* **F1.2 Adaptive Thermal Cutoff:** Automatically throttles fast-charging power when cell temperature hits 45°C, triggering emergency disconnect at 52°C.
* **F1.3 Dynamic ETA Engine:** Algorithmic prediction model updating charge completion time based on thermal throttling curves.

### Phase 2: Fleet Operations & Energy Optimization (Months 4–6)
* **F2.1 Dynamic ToU Load Shifting:** Automated charging scheduler prioritizing off-peak power grid hours based on utility tariff feeds.
* **F2.2 Staged Canary OTA Pipeline:** Progressive firmware updates rolled out sequentially (1% → 10% → 100%) with automated health checks and sub-second rollback.
* **F2.3 Fleet Operator Dashboard:** Unified web dashboard displaying real-time battery health, charging status, and site power draw.

### Phase 3: Predictive AI & Battery Analytics (Months 7–9)
* **F3.1 Predictive Thermal Pre-Conditioning:** ML model predicting station arrival and pre-cooling battery packs to optimal charging temperature (25°C).
* **F3.2 Battery Health (SoH) Diagnostic Engine:** Analytics module tracking cell internal impedance and capacity loss over time.
* **F3.3 Enterprise Multi-Brand SDKs:** Standardized adapter libraries for rapid onboarding of third-party OEM partner fleets.

### Phase 4: Enterprise Scale, Automation & Monetization (Months 10–12)
* **F4.1 Multi-Tenant B2B Billing System:** Usage-based billing system generating automated invoices based on kWh consumed and SaaS tier.
* **F4.2 OpenADR 2.0b Grid Integration:** Allows fleet depots to participate in automated utility demand-response events.
* **F4.3 Microservices High-Availability Scaling:** Cloud infrastructure optimization supporting 99.95% operational SLA across 100,000+ simultaneous connections.

---

## 4. Visual Timeline & Gantt Chart
+------------------------------------+----+----+----+----+----+----+----+----+----+----+----+----+
| Task Name                          | M1 | M2 | M3 | M4 | M5 | M6 | M7 | M8 | M9 |M10 |M11 |M12 |
+------------------------------------+----+----+----+----+----+----+----+----+----+----+----+----+
| PHASE 1: MVP CORE INFRASTRUCTURE   |    |    |    |    |    |    |    |    |    |    |    |    |
| - Telemetry Pipeline (OCPP/MQTT)   |████|████|    |    |    |    |    |    |    |    |    |    |
| - Thermal Safety Cutoff Engine     |    |████|████|    |    |    |    |    |    |    |    |    |
| - Dynamic Charging ETA Engine      |    |    |████|    |    |    |    |    |    |    |    |    |
| PHASE 2: FLEET OPERATIONS          |    |    |    |    |    |    |    |    |    |    |    |    |
| - Time-of-Use Load Shifting        |    |    |    |████|████|    |    |    |    |    |    |    |
| - Staged Canary OTA Pipeline       |    |    |    |    |████|████|    |    |    |    |    |    |
| - Fleet Operator Dashboard         |    |    |    |    |    |████|    |    |    |    |    |    |
| PHASE 3: PREDICTIVE AI & ML        |    |    |    |    |    |    |    |    |    |    |    |    |
| - Predictive Pre-Conditioning      |    |    |    |    |    |    |████|████|    |    |    |    |
| - Battery SoH Analytics Model      |    |    |    |    |    |    |    |████|████|    |    |    |
| - Multi-Brand Telemetry SDKs       |    |    |    |    |    |    |    |    |████|    |    |    |
| PHASE 4: ENTERPRISE SCALE          |    |    |    |    |    |    |    |    |    |    |    |    |
| - Multi-Tenant B2B Billing         |    |    |    |    |    |    |    |    |    |████|████|    |
| - Utility Demand Response (OpenADR)|    |    |    |    |    |    |    |    |    |    |████|████|
| - SLA Scaling & Security Hardening |    |    |    |    |    |    |    |    |    |    |    |████|
+------------------------------------+----+----+----+----+----+----+----+----+----+----+----+----+
---

## 5. Risk Assessment & Mitigation Plan

| Identified Risk | Severity | Likelihood | Mitigation Strategy |
| :--- | :---: | :---: | :--- |
| **Telemetry Ingestion Bottlenecks** | High | Medium | Implement Apache Kafka / Redis pub-sub layer to scale up to 100k events/sec. |
| **Firmware Update Bricking Risk** | Critical | Low | Mandatory automated canary deployments restricted to 1% fleet; hardware-level dual-bank flash rollback. |
| **Proprietary OEM Protocol Drift** | Medium | High | Enforce standardized OCPP 2.0.1 wrapper; offer open-source SDK adapters to OEM partners. |
| **Grid Power Tariff Gridlock** | Medium | Medium | Provide fallback static tariff schedules customizable by depot managers. |

---

## 6. Resource Allocation Plan

| Functional Role | Phase 1 (MVP) | Phase 2 | Phase 3 | Phase 4 |
| :--- | :---: | :---: | :---: | :---: |
| **Product Manager** | 1.0 FTE | 1.0 FTE | 1.0 FTE | 1.0 FTE |
| **Backend / Telemetry Engineers** | 3.0 FTE | 3.0 FTE | 4.0 FTE | 4.0 FTE |
| **Embedded / IoT / OTA Engineers**| 2.0 FTE | 2.0 FTE | 2.0 FTE | 2.0 FTE |
| **Data Scientists / AI Engineers** | 0.5 FTE | 1.0 FTE | 2.0 FTE | 2.0 FTE |
| **Frontend / UX Engineers** | 1.0 FTE | 2.0 FTE | 2.0 FTE | 2.0 FTE |
| **QA / Automation Engineers** | 1.0 FTE | 1.5 FTE | 2.0 FTE | 2.0 FTE |
| **Total Team Allocation** | **8.5 FTE** | **10.5 FTE** | **13.0 FTE** | **13.0 FTE** |
