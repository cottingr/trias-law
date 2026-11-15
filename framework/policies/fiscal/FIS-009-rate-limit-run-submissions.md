---
id: FIS-009
title: Rate Limit Run Submissions
domain: fiscal
status: proposed
scope: run-management
rules:
  - max_runs_per_minute: 60
  - burst_capacity: 120
  - penalty_on_exceed: delay_30_seconds
---
A per‑user rate limit of 60 runs per minute is imposed with a burst capacity of 120 runs. If a user exceeds the steady‑state limit, subsequent submissions are delayed by 30 seconds. This smooths out submission spikes, protects the scheduler, and reduces latency for all users.