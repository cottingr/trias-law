---
id: SEC-116
title: Constrain monitoring service accounts to log-read only
domain: security
status: proposed
scope: monitoring-service-accounts
rules:
  - least_privilege: "Service accounts may access logs via read‑only API; SSH host access is denied"
---
Monitoring service accounts are currently granted host‑level SSH access, which exceeds their functional need. This policy removes SSH permissions and restricts access to a read‑only logging API, mitigating lateral movement and credential misuse.