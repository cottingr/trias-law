---
id: REL-110
title: Close Monitoring Gaps for Latency‑Sensitive Services
domain: reliability
status: proposed
scope: monitoring-coverage
rules:
  - latency_alert_required: All services handling user‑visible latency (e.g., profile, search, recommendation) must expose a latency metric and have an alert threshold defined.
  - review_cycle: Monitoring definitions are reviewed quarterly to ensure coverage remains complete.
---
A policy to ensure that every latency‑sensitive service publishes a latency histogram and that an alert fires when the 95th‑percentile latency exceeds the service‑specific SLA. The monitoring team will audit and verify coverage every quarter, updating alerts as needed.
