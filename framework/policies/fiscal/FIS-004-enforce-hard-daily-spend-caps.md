---
id: FIS-004
title: Enforce Hard Daily Spend Caps per Model Tier
domain: fiscal
status: enacted
scope: model-tier-spending
rules:
  - limit_daily_spend: true
  - hard_cap_enforced: true
---
Fiscal spend for each model tier shall be tracked against a configurable daily ceiling. When the cap is reached, further runs on that tier are rejected until the next calendar day. The cap values are set by the Clerk and cannot be overridden by any executive component.
