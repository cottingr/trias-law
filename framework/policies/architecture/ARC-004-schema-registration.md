---
id: ARC-004
title: Schema Registration for Cross-Component Messaging
domain: architecture
status: proposed
scope: inter-component-messaging
rules:
  - register_schema: Every message type exchanged between components must have a schema defined in the Registry and referenced in the interface contract.
  - enforce_schema: Runtime message brokers shall validate payloads against the registered schema, rejecting non‑conforming messages.
---
All cross‑component messages must be described by a versioned schema stored in the central Registry. Publishers and subscribers must reference the schema identifier in their contract definitions. This prevents implicit contracts and ensures compatibility.