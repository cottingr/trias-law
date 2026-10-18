---
id: SEC-004
title: Prevent Encryption Key Leakage in Logs
domain: security
status: proposed
scope: logging
rules:
  - secret_mask: Encryption key identifiers and values are masked before being emitted to any logging sink.
  - audit: Logging configurations are audited weekly for accidental secret inclusion.
  - enforce: Logging agents reject events containing unmasked secret patterns.
---
Logging pipelines are updated to apply a masking filter for any field matching `*key*` or `*secret*`. An automated audit validates compliance and reports violations.
