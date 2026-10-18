---
id: SEC-002
title: Scope CI Secret Access to Declared Secrets
domain: security
status: proposed
scope: ci-pipelines
rules:
  - least_privilege: CI service accounts may read only the secrets explicitly declared in the pipeline definition.
  - secret_namespace: Secrets are segregated into `ci/<pipeline-name>` namespaces; cross‑pipeline access is denied.
  - audit: Access attempts to undeclared secrets trigger alerts and are logged.
---
CI pipelines must list required secrets in a manifest file. The CI runner enforces this manifest at runtime, refusing any secret fetch not enumerated therein. This limits secret exposure if a pipeline is compromised.
