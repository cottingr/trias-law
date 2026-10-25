---
id: REL-103
title: Prohibit unsanctioned restarts of shared services
domain: reliability
status: proposed
scope: service-restarts
rules:
  - require: Restart of any shared service must have explicit approval from the service owner and a documented rollback plan.
  - audit: All restart events are logged and reviewed within 24 hours by the reliability team.
---

**Rationale**
Evidence of unapproved restarts of the central caching layer caused latency spikes across multiple downstream services. Enforcing an approval workflow with a rollback plan will prevent accidental disruption of shared resources.
