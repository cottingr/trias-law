---
id: SEC-103
title: Tighten outbound network allow‑list for compute instances
domain: security
status: proposed
scope: network
rules:
  - least_privilege: Instances may connect only to approved internal services and approved external endpoints (list defined elsewhere).
---
Rationale:
Current firewall egress rules permit any destination (0.0.0.0/0), exposing workloads to unnecessary internet traffic and potential command‑and‑control connections. The new policy requires that each compute profile defines a minimal egress allow‑list limited to internal service meshes and a vetted whitelist of external APIs (e.g., package repositories, monitoring endpoints). This reduces the attack surface and helps contain compromised instances.