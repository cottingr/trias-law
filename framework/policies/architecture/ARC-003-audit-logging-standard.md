---
id: ARC-003
title: Standardize Audit Logging for Cross‑Component Interactions
domain: architecture
status: proposed
scope: cross-component-calls
rules:
  - mandatory_logging: Every inter‑service request and response must generate an immutable audit log entry containing timestamps, caller, callee, payload hash, and outcome.
  - retention_policy: Audit logs must be retained for a minimum of 2 years and protected against tampering.
  - centralized_storage: Logs are to be stored in the approved centralized log aggregation platform.
---
**Amendment Rationale**
Current logs omit the `user‑profile` → `analytics` interaction, creating a blind spot for data flow tracking. This amendment expands the existing ARC‑003 policy to cover all cross‑component calls and defines concrete retention and protection requirements.

**Implementation Guidance**
- Instrument service SDKs to emit structured log events to the central platform.
- Deploy a log integrity service that signs entries upon ingestion.
- Configure alerting for missing log entries detected by periodic reconciliation jobs.
