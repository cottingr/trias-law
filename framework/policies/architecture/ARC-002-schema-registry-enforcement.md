---
id: ARC-002
title: Mandate Schema Registry for Inter‑Service Messages
domain: architecture
status: proposed
scope: inter-service-communication
rules:
  - register_schema: Every message type exchanged between services must have a canonical JSON Schema registered in the central Schema Registry.
  - validate_schema: Sending services must validate outgoing payloads against the registered schema; receiving services must validate inbound payloads before processing.
  - versioning: Schema versions must be semver‑compatible and backward‑compatible where possible.
---
**Rationale**
The ad‑hoc payloads emitted by `notification‑engine` expose downstream services to unexpected fields or missing data, causing runtime errors. A mandatory schema registry guarantees contract stability and enables automated validation.

**Implementation Guidance**
- Deploy a shared Schema Registry service (e.g., Confluent Schema Registry).
- Extend each service’s message broker client to perform pre‑ and post‑validation.
- Enforce CI checks that reject commits introducing unregistered message types.
