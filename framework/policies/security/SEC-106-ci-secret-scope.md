---
id: SEC-106
title: Scope CI pipeline secret access to declared secrets only
domain: security
status: enacted
scope: ci-pipelines
rules:
  - least_privilege: CI jobs may read only the secrets explicitly declared in their pipeline definition.
  - secret_namespace: Secrets must be stored in a CI‑specific namespace and referenced via scoped identifiers.
---
Current CI pipelines have a blanket read permission on the entire secret store, allowing any pipeline to retrieve any secret. This policy limits access to only those secrets enumerated in the pipeline’s configuration, reducing exposure.