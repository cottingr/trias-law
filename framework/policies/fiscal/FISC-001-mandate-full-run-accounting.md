---
id: FISC-001
title: Mandate Full Run Accounting and Non-zero Timeout Billing
domain: fiscal
status: proposed
scope: system
rules:
  - all_executions_must_be_counted: true
  - timeout_charges_nonzero: true
  - audit_log_sync: true
---
**Rationale**
The ledger shows spend approaching the cap while timed‑out runs are occasionally omitted from secondary reports. This policy requires that every execution, including aborted and timed‑out runs, be recorded in the central accounting store and that a minimum non‑zero charge be applied. Synchronization of audit logs ensures downstream dashboards reflect the true cost, closing the leak identified in the observations.

**Implementation**
- Update the Execution Tracker to emit a `run_completed` event for every run state.
- Enforce a minimum charge of 0.1 % of the allocated token budget for any timeout.
- Add a nightly reconciliation job that flags mismatches between the accounting ledger and audit logs.
