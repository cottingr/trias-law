---
id: REL-104
title: Mandatory Post-Change Health Checks for Database Migrations
domain: reliability
status: proposed
scope: database
rules:
  - require: run health‑check suite after any schema change
  - require: verify replication lag < 5s within 2 minutes of migration completion
  - require: confirm read/write routing is healthy before traffic resume
---
This policy obligates all database schema or topology changes to be followed by an automated health‑check run. The checks must include replication lag, query latency variance, and error‑rate thresholds. If any check fails, the change is automatically rolled back and an incident is raised. Implementing this reduces outage risk from missing validation after migrations.