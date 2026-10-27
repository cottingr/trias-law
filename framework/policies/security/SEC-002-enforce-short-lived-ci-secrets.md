---
id: SEC-002
title: Enforce short‑lived CI secrets
domain: security
status: enacted
scope: ci-pipelines
rules:
  - least_privilege: CI jobs receive only the secrets they declare with a maximum TTL of 1 hour
---
CI pipelines presently have unrestricted read access to the entire secrets vault and retrieved secrets persist beyond the lifecycle of a job. This policy mandates that each pipeline explicitly declare required secrets, and that those secrets are minted with a time‑to‑live (TTL) no greater than one hour, after which they are automatically revoked.