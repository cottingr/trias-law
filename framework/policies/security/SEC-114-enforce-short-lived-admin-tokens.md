---
id: SEC-114
title: Enforce short-lived admin tokens for privileged actions
domain: security
status: proposed
scope: token-issuance
rules:
  - least_privilege: Privileged tokens must have a maximum TTL of 1 hour and require MFA for issuance
---
Long-lived administrative tokens broaden the attack surface. This policy mandates that any token granting admin-level privileges must be short-lived (≤1 hour) and issued only after multi-factor authentication, reducing risk of token misuse.