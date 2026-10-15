---
id: SEC-003
title: Restrict outbound allow‑list for Service A
domain: security
status: proposed
scope: service-a
rules:
  - least_privilege: Service A may only call whitelisted API endpoints defined in its manifest
---
Service A’s network policy currently permits outbound traffic to any internet address (0.0.0.0/0). This policy narrows the outbound allow‑list to only those API endpoints explicitly required by Service A, as documented in its deployment manifest, thereby reducing unnecessary exposure.