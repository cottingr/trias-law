---
id: SEC-005
title: Ensure unique privileged SSH keys per service
domain: security
status: enacted
scope: host-keys
rules:
  - least_privilege: Each service must have its own dedicated privileged SSH key pair; keys must never be shared across services
---
Privileged SSH host keys were found to be shared among multiple services, increasing the blast radius of a key compromise. This policy mandates generation of distinct privileged SSH key pairs for each service and enforces strict key rotation and audit to ensure keys are not reused across service boundaries.