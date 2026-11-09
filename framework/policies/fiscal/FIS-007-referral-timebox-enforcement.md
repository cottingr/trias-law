---
id: FIS-007
title: Referral Time‑Box Enforcement and Escalation
domain: fiscal
status: enacted
scope: referrals
rules:
  - max_referral_duration_minutes: 30
  - auto_escalate_on_overrun: true
  - charge_overrun_penalty_usd_per_minute: 0.05
---
Referral requests must complete within a 30‑minute time‑box. If a referral exceeds this window, it is automatically escalated to the Clerk and an overrun penalty is applied at $0.05 per additional minute. This ensures timely resolution and prevents indefinite resource consumption.
