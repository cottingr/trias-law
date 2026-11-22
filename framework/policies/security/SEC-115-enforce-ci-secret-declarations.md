---
id: SEC-115
title: Enforce per-pipeline secret declarations
domain: security
status: proposed
scope: ci-pipelines
rules:
  - least_privilege: "CI jobs may read only secrets explicitly declared in their pipeline configuration"
---
CI pipelines shall be required to list all secrets they need in the pipeline manifest. The CI system will enforce that only those declared secrets are accessible, denying any implicit or wildcard secret reads. This reduces exposure of unrelated secrets and aligns with the principle of least privilege.