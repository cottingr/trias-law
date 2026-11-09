---
id: SEC-110
title: Enforce least-privilege IAM roles for service accounts
domain: security
status: enacted
scope: service-accounts
rules:
  - least_privilege: Service accounts must be assigned roles that only permit actions required for their function, avoiding broad roles like "editor" or "owner"
---
Rationale: Service accounts are frequently used by applications and automation. Assigning them only the permissions they truly need reduces the chance of privilege escalation, limits potential damage from compromised credentials, and aligns with the estate’s overall attack surface reduction strategy.