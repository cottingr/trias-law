---
id: FIS-006
title: Minimum Charge for Timed‑Out Runs
domain: fiscal
status: proposed
scope: billing
rules:
  - enforce_minimum_charge: true
  - minimum_charge_usd: 0.01
  - apply_to_all_timeouts: true
---
Any run that terminates due to a timeout shall incur a minimum charge of $0.01, ensuring that no timed‑out run is billed as zero. This rule applies uniformly across all model tiers and cannot be waived by advisory components.
