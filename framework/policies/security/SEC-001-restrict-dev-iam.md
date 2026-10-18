---
id: SEC-001
title: Restrict Developer IAM Role to Required Buckets
domain: security
status: proposed
scope: iam-roles
rules:
  - least_privilege: Developers receive read‑only access to analytics bucket and read/write access only to their own feature‑branch buckets.
  - deny_all_else: All other S3 bucket actions are denied unless explicitly whitelisted per project.
---
The existing `dev-full` role is pruned to the minimal bucket permissions required for each team. A per‑team policy block is introduced, and future role expansions must be justified through a documented access request.
