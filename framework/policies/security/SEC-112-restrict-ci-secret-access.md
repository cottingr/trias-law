---
id: SEC-112
title: Restrict CI pipeline secret access to declared secrets
domain: security
status: proposed
scope: ci-pipelines
rules:
  - least_privilege: CI jobs may only read secrets explicitly declared in their pipeline definition
---
CI pipelines often request broad secret read permissions, exposing unrelated credentials. This policy enforces that each CI job must declare the exact secrets it needs, and the CI system shall grant read access only to those secrets, preventing inadvertent exposure.