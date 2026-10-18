---
id: ARC-001
title: Enforce Gate Token on All Action Paths
domain: architecture
status: proposed
scope: all-services
rules:
  - require_gate_token: All requests that trigger state‑changing actions must present a valid Gate token verified by the deterministic layer.
  - token_auditing: Gate token validation events must be recorded in the central audit log.
---
**Rationale**
All state‑changing operations must flow through the deterministic Gate to ensure proper authorization, accountability, and deterministic replay. This policy closes the observed bypass by `order‑processor` and prevents future unauthorized writes.

**Implementation Guidance**
- Integrate the Gate middleware into every service’s entry point for write APIs.
- Reject any request lacking a token with HTTP 401.
- Emit an audit record containing token ID, caller service, and target resource.
