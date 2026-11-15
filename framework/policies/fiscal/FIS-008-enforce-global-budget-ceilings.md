---
id: FIS-008
title: Enforce Global Budget Ceilings
domain: fiscal
status: proposed
scope: budget
rules:
  - monthly_budget_cap: 1000000
  - enforce_allocation: true
  - alert_threshold: 0.85
---
All spend is now required to stay beneath a hard monthly cap. The system will automatically halt new runs that would cause the cap to be exceeded and will issue alerts once 85% of the cap is reached. Allocation enforcement ensures that each model tier receives a defined budget slice, preventing a single tier from monopolising resources.