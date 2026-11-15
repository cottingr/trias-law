---
id: REL-106
title: Sequential Update Policy for Redundant Pair Members
domain: reliability
status: proposed
scope: infra-redundancy
rules:
  - require: updates to redundant pair members must be performed one at a time
  - require: health verification of the first member before proceeding to the second
  - require: maintain a rollback plan for each member and document it in the change ticket
---
Simultaneous updates of redundant pair members have produced split‑brain scenarios. This policy mandates a strict sequential update process with health verification between steps, preserving high availability and data consistency.