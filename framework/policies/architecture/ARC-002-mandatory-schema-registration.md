---
id: ARC-002
title: Mandate Schema Registration for All Inter-Component Messages
domain: architecture
status: proposed
scope: message-schema
rules:
  - register_schema: Every event or command exchanged between components must have an entry in the central schema registry before deployment.
  - enforce_version: Consumers must validate incoming payloads against the registered schema version and reject mismatches.
---
**Rationale**

Observations show that messages such as `ShipmentCreated` were emitted without a registered schema, leading to consumer errors and hidden data contract drift. A definitive, version‑controlled schema registry guarantees that all parties share a single source of truth for message shapes, enabling safe evolution and automated compatibility checks.

**Implementation notes**

* Integrate CI pipelines with the schema registry API to enforce registration as a build‑time check.
* Extend the message broker middleware to perform schema validation on publish and subscribe paths.
* Define a fallback policy that discards or dead‑letters messages failing validation, with alerts to the engineering on‑call.

**Compliance**

All teams must add a `schema.yaml` definition for each new message type and submit it via the `schema-registry` CI gate. Existing unregistered messages must be retro‑fitted within a 45‑day remediation window.
