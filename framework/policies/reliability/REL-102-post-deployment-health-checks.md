---
id: REL-102
title: Mandatory post‑deployment health checks for critical services
domain: reliability
status: proposed
scope: post-deployment
rules:
  - require: Deployments to critical services must run a health‑check suite within five minutes of completion.
  - metrics: Verify latency < 100 ms, error‑rate < 0.1 %, and CPU usage < 80 % for a sustained two‑minute window.
  - block: If any metric fails, an automated rollback is triggered.
---

**Rationale**
Critical systems (order‑processor, payment‑gateway, inventory‑sync) currently lack enforced verification after a release. By mandating a fast health‑check window, regressions are caught before they affect customers, and the rollback path is exercised automatically.
