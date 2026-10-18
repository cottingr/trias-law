---
id: FISC-002
title: Establish Frontier Model Tier Budget and Rate Limits
domain: fiscal
status: proposed
scope: model-tier
rules:
  - quarterly_budget_cap_frontier: 120M
  - per_user_monthly_limit: 30M
  - max_concurrent_runs_per_user: 10
  - burst_rate_limit: 1000 runs per minute
---
**Rationale**
Run clustering showed 18 % of executions within a short window, threatening rate‑limit saturation and allowing a few users to dominate frontier tier resources. By setting explicit quarterly caps, per‑user monthly limits, and concurrency/burst thresholds, we protect the budget while keeping the frontier tier available for high‑impact tasks.

**Implementation**
- Extend the quota service with per‑user counters for frontier tier usage.
- Introduce a token bucket algorithm that enforces the burst rate limit.
- Emit alerts when a user approaches the monthly limit or when the system approaches the quarterly cap.
