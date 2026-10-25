---
id: ARC-001
title: Enforce Gate Token on All Inter-Service Actions
domain: architecture
status: proposed
scope: inter-service-communication
rules:
  - require_gate_token: All calls between services must present a validated Gate token.
  - audit_trail: Every successful Gate token validation must be logged with actor, target, and timestamp.
---
**Rationale**

The current architecture mandates that the deterministic layer (the Gate) be the sole path to action. Recent logs show services bypassing this gate, exposing privileged functionality to unverified callers. Enforcing a mandatory Gate token on every inter‑service request restores the intended trust boundary, ensures consistent authorization checks, and provides a verifiable audit trail for all state‑changing operations.

**Implementation notes**

* Extend the service mesh or API gateway to inject and verify a signed `X-Gate-Token` header on every outbound request.
* Reject any request lacking a valid token with HTTP 401.
* Emit a structured audit event (`gate.validation`) to the centralized logging pipeline upon each successful validation.

**Compliance**

All new services must adopt the token‑validation middleware before production deployment. Existing services will be phased in over a 30‑day window with automated regression tests to ensure no functional regression.
