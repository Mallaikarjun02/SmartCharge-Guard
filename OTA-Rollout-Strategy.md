# OTA Rollout Strategy

## Release stages
1. Internal validation
2. Controlled pilot
3. 5% fleet
4. 25%
5. 50%
6. 100%

Percentages are illustrative. Actual rollout follows OEM governance.

## Monitoring
Track:
- OTA installation success
- rollback rate
- charging completion
- support contacts
- error events
- customer satisfaction

## Stop criteria
Pause rollout if:
- safety-related anomaly appears
- rollback exceeds threshold
- charging completion materially deteriorates
- customer complaints spike
- telemetry integrity is compromised

## Rollback principle
The system must have a validated recovery path. Safety-critical vehicle control must remain available independent of cloud connectivity.
