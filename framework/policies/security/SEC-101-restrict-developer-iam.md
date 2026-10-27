---
id: SEC-101
title: Restrict developer IAM privileges to least‑privilege scoped actions
domain: security
status: proposed
scope: iam
rules:
  - least_privilege: Developers receive only permissions required for their project resources, no wildcard actions.
---
Rationale:
Developers currently hold wildcard IAM permissions that allow read, write, and delete across the entire cloud project. This broad access increases the risk of accidental or malicious modification of unrelated resources. The proposed policy introduces scoped IAM role definitions that grant only the actions explicitly needed for a developer's assigned projects, enforcing the least‑privilege principle and reducing potential impact of credential compromise.