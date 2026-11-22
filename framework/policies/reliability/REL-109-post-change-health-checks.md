---
id: REL-109
title: Enforce Post‑Change Health Checks for Critical Services
domain: reliability
status: proposed
scope: post-change-validation
rules:
  - health_check_suite: After any change to a service classified as "critical", a predefined health‑check suite (readiness, liveness, latency, error‑rate) must run and pass before the change is marked successful.
  - rollback_on_failure: If any health check fails, the system must automatically initiate the documented rollback procedure.
---
Critical services (payment processing, user authentication, billing) must be verified through an automated health‑check suite immediately after a change. The suite includes metrics that reflect the service's core SLAs. Failure triggers an automatic rollback to the last known good version, preserving availability.
