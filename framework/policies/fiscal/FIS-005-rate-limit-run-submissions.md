---
id: FIS-005
title: Rate‑Limit Run Submissions and Detect Burst Clustering
domain: fiscal
status: proposed
scope: run-rate
rules:
  - max_runs_per_minute: 1200
  - burst_detection_window_seconds: 120
  - auto_throttle_on_burst: true
---
All run submissions are subject to a hard per‑minute limit. A burst detection window monitors submission spikes; if a burst is detected, the system automatically throttles new runs until the rate falls below the configured threshold. Violations are logged and reported to the Clerk for audit.
