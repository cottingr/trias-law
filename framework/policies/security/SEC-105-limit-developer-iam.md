---
id: SEC-105
title: Limit developer IAM privileges to least privilege
domain: security
status: enacted
scope: developer-accounts
rules:
  - least_privilege: Developers receive only permissions required for their project tasks, removing broad admin or Owner roles.
---
Developers currently possess the Owner role across the cloud environment, granting unrestricted access to compute, storage, networking, and secret management. This exceeds the principle of least privilege and increases the risk of accidental or malicious changes. The policy mandates role reassignment to project‑specific roles and removal of inherited wildcard permissions.