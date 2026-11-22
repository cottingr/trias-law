---
id: REL-108
title: Mandatory Dual‑Owner Approval for Redundant Pair Changes
domain: reliability
status: proposed
scope: change-management
rules:
  - require_two_distinct_owners: Any change that touches both members of a redundant pair must be approved by two owners from different teams.
  - audit_log: All dual‑owner approvals must be recorded in the change‑audit system.
---
To prevent simultaneous loss of redundancy, any deployment that modifies both members of a redundant pair (e.g., primary/secondary databases, active/passive load‑balancers) must receive explicit approval from two distinct owners, ideally from separate functional teams. Approvals are logged for auditability. Non‑compliant changes will be rejected by the deployment gate.
