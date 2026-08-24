# Product Requirements Document — SmartCharge Guard

## 1. Problem statement
When charging conditions change, users may experience lower charging power or a longer completion time without understanding why. This can create perceived defects and support demand.

## 2. User story
**As an EV owner, I want to understand why charging performance changed and know when my vehicle will finish charging, so that I can plan my trip confidently.**

## 3. Functional requirements
### FR-01 Adaptive state
The vehicle/system shall classify charging into approved states such as Normal, Optimizing and Fault/Service Required.

### FR-02 Dynamic ETA
The customer interface shall update expected completion time when charging conditions materially change.

### FR-03 Explanation
The interface shall provide a concise explanation for meaningful charging adjustments.

### FR-04 Telemetry
The system shall record charging-session events required for product analytics and approved diagnostics.

### FR-05 OTA
The capability shall support staged rollout, monitoring and rollback according to OEM release governance.

### FR-06 Safety boundary
Cloud/mobile services shall not replace validated local BMS safety controls.

## 4. Non-functional requirements
- High reliability
- Secure OTA delivery
- Privacy-aware telemetry
- Graceful connectivity degradation
- Clear severity hierarchy
- Auditable product events

## 5. Acceptance criteria
### AC-01
Given a charging session, when approved vehicle logic enters an adaptive state, the customer sees the updated charging status.

### AC-02
When ETA changes materially, the ETA is recalculated and presented clearly.

### AC-03
When an informational adjustment occurs, the user receives a non-alarming explanation.

### AC-04
If connectivity is unavailable, safety-critical vehicle behaviour continues locally.

### AC-05
If an OTA release exceeds predefined failure thresholds, rollout pauses or rolls back according to release policy.

## 6. Illustrative UX message
“Charging optimized for battery temperature. Charging speed has been temporarily adjusted. Updated completion time: 34 minutes.”

This wording is illustrative and must be validated with UX research.
