---
id: SEC-107
title: Enforce short‑lived service account keys
domain: security
status: enacted
scope: service-accounts
rules:
  - key_rotation: Service account keys must have a maximum lifespan of 30 days and be rotated automatically.
  - revocation: Expired keys are revoked immediately and audit logged.
---
Long‑lived service account keys remain active indefinitely, presenting a persistent attack vector. This policy introduces automatic expiration and rotation to mitigate credential theft.