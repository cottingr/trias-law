---
id: FIS-002
title: Impose Run Rate Limits and Execution Time Boxes
domain: fiscal
status: proposed
scope: execution
rules:
  - max_qps: 120
  - burst_window: 10m
  - burst_multiplier: 2
  - max_runtime: 45m
  - timeout_charge_floor: 0.01_USD_per_minute
---
**Rationale**
Run submissions are clustering in 10‑minute bursts that push QPS 150 % above the average, causing queue congestion and higher per‑run costs. By defining a maximum QPS of 120 with a controlled burst window, we smooth traffic and keep scheduler latency predictable. A hard execution time box of 45 minutes prevents runaway runs from inflating costs, while a minimal timeout charge floor eradicates zero‑charge loopholes.

**Implementation**
- The Intake service enforces the QPS and burst limits, returning a 429 response when exceeded.
- The scheduler aborts any run exceeding the 45 minute runtime, logging the event for audit.
- Billing logic applies the 0.01 USD/minute floor to any timed‑out run, ensuring honest revenue capture.
