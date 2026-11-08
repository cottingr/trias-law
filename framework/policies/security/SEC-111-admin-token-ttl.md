---
id: SEC-111
title: Short-lived admin access tokens
domain: security
status: proposed
scope: admin-access
rules:
  - token_ttl: Admin access tokens must have a maximum TTL of 1 hour and require MFA for renewal
---
Rationale: Administrative privileges should be granted only for the minimal time necessary. Enforcing a one‑hour maximum lifetime and MFA renewal dramatically narrows the window in which stolen admin credentials can be abused, thereby tightening host‑reach controls.