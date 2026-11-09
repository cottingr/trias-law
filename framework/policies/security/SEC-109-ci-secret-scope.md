---
id: SEC-109
title: Scope CI pipeline secret access to declared needs
domain: security
status: proposed
scope: ci-pipelines
rules:
  - least_privilege: Pipelines may only request and read secrets explicitly declared in their job definition
---
Rationale: By limiting CI jobs to the secrets they explicitly declare, we prevent accidental or malicious exposure of unrelated credentials, reduce the blast radius of a compromised pipeline, and enforce the principle of least privilege for automated workflows.