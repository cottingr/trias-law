---
id: FIS-010
title: Model Tier Assignment Policy
domain: fiscal
status: proposed
scope: model-tier
rules:
  - frontier_tier: executive_prompt_only
  - advisory_tier: batch_and_advisory_jobs
  - economy_tier: low_cost_tasks
  - enforce_assignment: true
---
The frontier tier is reserved exclusively for executive‑level prompts, preventing high‑cost usage by batch or advisory workloads. Advisory tier runs are limited to batch and advisory jobs, while the economy tier handles all low‑cost, high‑throughput tasks. Automatic enforcement ensures each run is routed to the correct tier based on its declared purpose, preserving budget integrity and optimizing resource allocation.