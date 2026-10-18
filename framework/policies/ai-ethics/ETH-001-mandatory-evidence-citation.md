---
id: ETH-001
title: Mandatory Evidence Citation and Confidence Disclosure for AI Reports
domain: ai-ethics
status: proposed
scope: ai-reports
rules:
  - require: Every AI‑generated advisory must include a citation to the underlying data or model shard that supports each claim
  - require: Confidence intervals (or a qualitative confidence label) must be attached to every factual assertion
  - require: Any speculative or inferential statement must be explicitly marked as a guess or hypothesis
  - require: When an agent cannot verify a claim, it must clearly state the limitation and refrain from presenting it as a recommendation
---
Rationale:
Current AI advisory practices lack the transparency needed for accountable decision‑making. By mandating evidence citations and confidence disclosures, the Arbiter receives a clear signal about the reliability of each recommendation, reducing the chance that unchecked AI output will be used to justify expanded agent authority. This policy also creates a documented audit trail that can be reviewed for compliance, helping to keep agent influence narrow and evidence‑based.

Implementation Notes:
- Integrate a citation metadata field into the AI report schema.
- Provide a standardized confidence taxonomy (e.g., high, medium, low or numeric probability ranges).
- Update the AI agent runtime to enforce these checks before emitting any advisory.
- Establish a periodic audit process to verify adherence.
