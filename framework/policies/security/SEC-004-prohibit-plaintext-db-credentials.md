---
id: SEC-004
title: Prohibit plaintext database credentials in source control
domain: security
status: proposed
scope: code-repositories
rules:
  - secret_handling: Database credentials must be stored only in secret management systems and referenced via environment variables or secret injection mechanisms
---
Plaintext database credentials were discovered in version‑controlled repositories, violating secret handling policies. This policy requires that all database credentials be stored exclusively in approved secret management solutions (e.g., Vault, AWS Secrets Manager) and accessed by applications through secure injection methods, eliminating direct inclusion in codebases.