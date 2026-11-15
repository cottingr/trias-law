---
id: ARC-003
title: Mandatory Gate Token for Action Invocation
domain: architecture
status: proposed
scope: inter-component-actions
rules:
  - require_gate_token: All component-to-component action calls must present a valid Gate token verified by the deterministic layer.
---
All components must acquire a Gate token from the deterministic layer before invoking any operation that changes state. The deterministic layer shall validate token authenticity and scope. Direct calls bypassing the Gate are prohibited and must be rejected at runtime.