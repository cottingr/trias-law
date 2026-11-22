---
id: FIS-012
title: Standardize Referral Run Time Boxes and Cost Honesty
domain: fiscal
status: proposed
scope: referral-service
rules:
  - max_run_time_minutes: 30
  - cost_minimum: 0.01
  - forbid_zero_charge_timeouts: true
---
Referral runs must complete within 30 minutes. Any timed‑out run is charged a minimum fee of $0.01 to prevent zero‑cost abuse. Runs exceeding the time box are terminated and flagged for review.