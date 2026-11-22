---
id: ARC-007
title: Centralize policy repository and forbid unauthorized copies
domain: architecture
status: proposed
scope: policy-management
rules:
  - single_source: the framework/policies/architecture directory is the sole authoritative source for architecture policies
  - deny_copy: any duplicate policy files outside this directory are prohibited and must be removed automatically
---
All architecture policies must reside exclusively in the `framework/policies/architecture` directory. Creation of policy copies in other repositories or directories is disallowed. Automated checks will purge unauthorized duplicates to maintain a single source of truth.