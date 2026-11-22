---
id: AIE-004
title: Require explicit uncertainty disclosure and evidence citation in all agent reports
domain: ai-ethics
status: proposed
scope: all-agent-reports
rules:
  - agents must cite verifiable sources for any factual claim they make
  - agents must include a confidence level (e.g., high, medium, low) for each claim
  - agents must label any speculative or guess‑based statements as "hypothesis" or "estimate"
  - agents must explicitly state when a claim cannot be verified with available data
  - reports must avoid language that nudges decision‑makers toward granting additional privileges without justification
---
## Rationale

The AI system increasingly influences operational decisions across the platform. To preserve human oversight and prevent unintended authority expansion, it is essential that agents be transparent about the certainty of their statements and the evidential basis for their conclusions. By mandating source citations, confidence indicators, and clear labeling of speculation, stakeholders can better assess risks, audit AI behavior, and resist pressure to grant agents broader privileges based on opaque assertions.

## Implementation Notes

* Existing logging and response frameworks will be extended to capture source URLs, confidence scores, and uncertainty flags.
* UI components presenting AI output to users will highlight speculative content and display confidence tiers.
* Non‑compliance will be logged and trigger a review workflow before any downstream actions are taken.
