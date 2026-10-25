---
id: TIM-003
title: Mandatory Time‑Boxing and Honest Billing for Runs
domain: fiscal
status: proposed
scope: billing
rules:
  - min_charge: "All runs, including timeouts, are billed at least the minimum unit cost of $0.001 per second."
  - timebox_limits: "Frontier runs: max 30 seconds; Batch runs: max 2 minutes; Advisory runs: max 5 minutes."
  - auto‑truncate: "Runs exceeding the time‑box are automatically terminated and billed for the full allowed duration."
  - audit: "Clerk performs weekly audits to ensure no zero‑charge timeouts exist."
---
The policy guarantees revenue integrity by enforcing a minimum charge on every run, even if it times out. Distinct time‑boxes per tier protect against runaway compute consumption while preserving fairness across users.