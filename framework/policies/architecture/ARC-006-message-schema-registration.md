---
id: ARC-006
title: Register and validate schemas for all inter-service messages
domain: architecture
status: proposed
scope: inter-service-communication
rules:
  - schema_registry: every message type exchanged via EventBus or RPC must have a versioned JSON schema defined in the central registry
  - validation: sending and receiving components must validate messages against their schema before processing
---
Each inter‑service message must be accompanied by a schema entry in the central Schema Registry. Publishers and consumers are required to perform schema validation at send‑ and receive‑time, preventing type mismatches and ensuring downstream safety.