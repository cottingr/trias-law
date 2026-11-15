---
id: REL-105
title: Dual‑Approval Requirement for Shared Service Restarts
domain: reliability
status: proposed
scope: shared-services
rules:
  - require: a ticket with two independent approvers before restarting any shared service (e.g., cache, message bus)
  - require: post‑restart verification of service health metrics for 5 minutes
  - require: capture restart signature in change‑log for audit
---
Shared services such as Redis, Kafka, and etcd serve many downstream systems. Restarting them without coordination can cause cascading failures. This policy enforces a dual‑approval workflow and a short‑window health check after the restart, ensuring stability and traceability.