---
id: FIS-003
title: Assign Model Tiers and Ensure Honest Cost Billing
domain: fiscal
status: enacted
scope: model-management
rules:
  - frontier_tier: exclusive to executive workloads
  - batch_tier: limited to non‑real‑time jobs
  - advisory_tier: restricted to cost‑effective advisory queries
  - cost_reporting: every run must report actual compute seconds consumed
  - surcharge_on_misreport: 20% penalty for under‑reporting
---
**Rationale**
Current model‑tier assignments blur the line between frontier (high‑cost) and batch/advisory (economy) workloads, leading to cost leakage. Explicit tier definitions keep the executive layer on the frontier tier, while batch and advisory workloads stay on economy tiers. Mandatory reporting of actual compute seconds prevents under‑billing, and a punitive surcharge deters misreporting.

**Implementation**
- Update the Model Registry to tag each model with its designated tier.
- Intake validates that a request's tier matches the workload type; mismatches are rejected.
- Billing modules record the exact compute seconds per run and compare against the declared estimate.
- If the declared estimate is lower than actual by >5 %, apply the 20 % surcharge to the billed amount.
