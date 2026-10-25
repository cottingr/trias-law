---
id: REL-101
title: Dual-owner approval for redundant pair changes
domain: reliability
status: proposed
scope: change-management
rules:
  - require: At least two distinct owners must approve any change that touches a member of a redundant pair.
  - enforce: Automated checks reject PRs lacking dual signatures.
---

**Rationale**
Multiple incidents have shown that a change affecting only one side of a redundant pair can inadvertently introduce a failure mode that propagates when the other side is later impacted. Requiring dual‑owner approval ensures independent review and reduces the chance of accidental outages.
