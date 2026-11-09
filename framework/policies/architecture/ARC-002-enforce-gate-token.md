---
id: ARC-002
title: Enforce Gate Token for All Inter‑Service Actions
domain: architecture
status: enacted
scope: inter-service-communication
rules:
  - require_gate_token: true
  - deny_schema_missing: true
---
This policy mandates that any request crossing component boundaries must present a valid Gate token issued by the deterministic layer and must conform to a registered message schema. All services must reject requests that lack a token or a matching schema, and any deviation will be logged and trigger an alert. Enforcement is applied at the API gateway level to ensure a single immutable path to action.