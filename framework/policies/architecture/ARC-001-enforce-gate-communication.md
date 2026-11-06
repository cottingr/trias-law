---
id: ARC-001
title: Enforce Gate-Only Inter-Component Communication
domain: architecture
status: enacted
scope: inter-component
rules:
  - require_gate_token: All service-to-service calls must include a valid Gate token.
  - schema_registry: Every message type must be registered in the central schema registry with versioning.
  - audit_logging: All cross-component interactions must be logged with immutable audit entries.
---
All service interactions must be mediated through the deterministic Gate layer. Direct library calls, shared memory access, or undocumented HTTP endpoints that bypass the Gate are prohibited. Teams must define a schema for each message in the central registry and reference it in their interface contracts. The system will reject any deployment that contains calls without a verified Gate token, and runtime enforcement will log attempts and abort unauthorized paths. This policy preserves separability, ensures traceability, and prevents privilege expansion without proper oversight.
