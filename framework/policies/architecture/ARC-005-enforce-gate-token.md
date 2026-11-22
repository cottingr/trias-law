---
id: ARC-005
title: Require Gate token for all state-modifying operations
domain: architecture
status: proposed
scope: deterministic-layer
rules:
  - enforce: all components must acquire a Gate token before performing any write or mutation action
---
All components must call the deterministic layer's Gate service to obtain a token that encodes the action, actor, and timestamp. Direct database or storage access without a token is prohibited and will be logged as a violation.