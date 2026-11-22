---
id: SEC-117
title: Ban hard‑coded secret identifiers in repositories
domain: security
status: proposed
scope: code-repositories
rules:
  - secret_handling: "Repositories must not contain raw secret identifiers; use secret reference mechanisms provided by secret manager"
---
Embedding secret IDs in source code creates a vector for secret enumeration and exfiltration. Developers must use the secret manager's reference syntax and ensure secret IDs are not checked into version control. Automated scans will enforce this rule.