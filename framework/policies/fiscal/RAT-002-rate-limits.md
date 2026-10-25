---
id: RAT-002
title: Standardize Run Rate Limits per Model Tier
domain: fiscal
status: proposed
scope: run-management
rules:
  - tier_limits:
      frontier: "max 150 runs per minute"
      batch: "max 80 runs per minute"
      advisory: "max 40 runs per minute"
  - burst_handling: "Burst requests exceeding tier limits are queued with a maximum wait time of 30 seconds before rejection."
  - enforcement: "Intake service rejects requests that would violate the active tier limit; the Clerk logs each rejection."
---
This policy assigns concrete run‑rate ceilings to each model tier, preventing resource contention during demand spikes. Bursts are either queued within a bounded window or rejected, ensuring predictable performance and cost predictability.