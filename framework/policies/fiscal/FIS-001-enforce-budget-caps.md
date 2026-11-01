---
id: FIS-001
title: Enforce Periodic Budget Caps and Full Accounting
domain: fiscal
status: proposed
scope: system-wide
rules:
  - daily_cap: 10_000_000_USD
  - enforce_full_count: every run must be recorded before budget aggregation
  - alert_threshold: 98% of daily_cap triggers automatic spend freeze
  - audit_window: 24h rolling audit of spend vs cap
  - remediation: auto‑scale down non‑critical workloads when cap breach risk persists > 2h
---
**Rationale**
The Ledger indicates that daily spend repeatedly approaches the 10 M‑USD ceiling. A hard daily cap, combined with a transparent audit window, prevents accidental overspend and forces proactive throttling. Automatic alerts at 98 % utilization give operations enough time to act before the cap is breached, while a forced freeze protects fiscal health.

**Implementation**
- Integrate the cap check into the Intake service; reject new runs once the cap would be exceeded.
- The Clerk logs every run before budget aggregation to guarantee a complete count.
- Provide dashboards for real‑time cap consumption and breach alerts.
