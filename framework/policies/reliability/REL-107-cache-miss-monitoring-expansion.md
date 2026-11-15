---
id: REL-107
title: Expand Monitoring Coverage for Cache Miss Latency
domain: reliability
status: proposed
scope: cache
rules:
  - require: add latency SLO for cache‑miss responses (≤ 100 ms 99th percentile)
  - require: alert on cache‑miss latency breach lasting > 2 minutes
  - require: capture cache‑miss rates per service for root‑cause analysis
---
Current monitoring lacks visibility into cache‑miss latency, which contributed to the recent outage when the Redis service was restarted. This policy extends observability to cache‑miss metrics and defines alerting thresholds to catch degradations early.