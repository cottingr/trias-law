---
id: FISC-003
title: Implement Referral Execution Timeboxes and Cost Transparency
domain: fiscal
status: proposed
scope: referrals
rules:
  - max_referral_duration: 24h
  - cost_cap_per_referral: 5M
  - automatic_termination_on_exceed: true
  - reporting_of_referral_costs: true
---
**Rationale**
Referral tickets in the period exceeded 48 hours and accumulated 1.8 M token cost, indicating uncontrolled execution time and budget exposure. This policy caps each referral's runtime and cost, automatically terminates overruns, and requires that all referral costs be reported in the public fiscal dashboard.

**Implementation**
- Add a watchdog service that monitors referral runtimes and costs.
- On exceeding the 24 h or 5 M token thresholds, terminate the referral job and flag it for review.
- Extend the fiscal reporting UI to include a per‑referral cost breakdown.
