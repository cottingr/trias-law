---
id: SEC-108
title: Namespace application secrets with explicit allow‑lists
domain: security
status: enacted
scope: secret-management
rules:
  - namespace_isolation: Each application receives its own secret namespace; cross‑namespace reads are prohibited.
  - allow_list: Applications may be granted read access to another namespace only via an explicit allow‑list entry reviewed by security.
---
Secrets are currently stored in a flat structure, enabling any service with read permission to access all secrets. This policy enforces isolation and controlled sharing.