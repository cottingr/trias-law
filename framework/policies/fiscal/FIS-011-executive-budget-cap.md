---
id: FIS-011
title: Enforce Frontier Tier Budget Ceiling
domain: fiscal
status: proposed
scope: model-executive
rules:
  - max_monthly_budget: 500000
  - enforce_full_count: true
  - alert_threshold: 0.9
---
This policy sets a hard monthly budget ceiling for the frontier model tier at $500,000. All runs, including timed‑out and zero‑cost anomalies, are counted toward the total. Alerts fire at 90 % utilization and execution is paused if the ceiling is reached.