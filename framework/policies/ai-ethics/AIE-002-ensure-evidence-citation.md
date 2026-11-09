---
id: AIE-002
title: Mandate evidence citation, confidence labeling, and uncertainty disclosure
domain: ai-ethics
status: enacted
scope: ai-responses
rules:
  - require: All AI statements that influence policy or agent actions must cite supporting evidence or note when evidence is unavailable.
  - require: Each statement must include a confidence level (high/medium/low) expressed in a standard format.
  - require: Guesses must be explicitly labeled as such, and alternatives must be presented when uncertainty exists.
  - require: Systems must log any inability to verify claims for audit purposes.
---

### Rationale

Transparent AI communication is essential to prevent implicit authority expansion. By requiring evidence citations, confidence scores, and clear uncertainty markers, stakeholders can assess the reliability of AI advice and make informed decisions about granting agents additional privileges. The accompanying audit log ensures that any unverifiable claims are traceable, supporting oversight and accountability.

### Implementation Notes

* Integrate citation and confidence fields into existing response schemas.
* Define a standard confidence taxonomy (e.g., high ≥ 90%, medium 60‑89%, low < 60%).
* Log entries should include timestamp, request identifier, cited sources, confidence level, and a flag for unverifiable statements.
