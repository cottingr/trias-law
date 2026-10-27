---
id: SEC-102
title: Enforce secret namespace segregation per service
domain: security
status: enacted
scope: secrets
rules:
  - least_privilege: Each service may read secrets only within its own `service/<name>/` namespace.
---
Rationale:
Audit logs show services accessing secret keys outside of their own namespace, creating a pathway for credential leakage and lateral movement. This policy mandates that secret stores (e.g., Vault, Parameter Store) enforce a hierarchical namespace scheme where a service's identity is mapped to a distinct prefix. Access control lists must be defined so that a service can only read keys under its own prefix, eliminating unintended cross‑service secret visibility.