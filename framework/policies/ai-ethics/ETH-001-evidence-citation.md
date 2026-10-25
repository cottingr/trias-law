---
id: ETH-001
title: Evidence citation and confidence labeling requirement
domain: ai-ethics
status: proposed
scope: agent_output
rules:
  - require_citation: All factual statements must reference a verifiable source or dataset.
  - require_confidence: Every claim must include a confidence level (high, medium, low) expressed numerically (e.g., 0.92).
  - label_speculation: Statements that are educated guesses must be clearly labeled as "speculation".
  - disclose_unknowns: Agents must explicitly note when they cannot verify a claim or lack sufficient data.
---
Rationale:
This policy ensures that AI agents provide transparent, accountable output. By mandating citations, confidence metrics, and clear speculation labeling, users can gauge reliability and the system cannot covertly nudge decision‑makers toward granting more authority based on unverified assertions.

Implementation notes:
* Integrate a citation‑format checker into the response generation pipeline.
* Require the confidence field in the response JSON schema.
* Add a "speculation" flag that triggers a visual cue in UI displays.

Compliance will be audited quarterly by the AI Ethics Board.