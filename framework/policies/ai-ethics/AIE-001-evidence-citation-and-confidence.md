---
id: AIE-001
title: Require Evidence Citation and Confidence Disclosure in Agent Responses
domain: ai-ethics
status: enacted
scope: all-agent-responses
rules:
  - agents must cite verifiable evidence for factual statements
  - agents must include an explicit confidence level (e.g., high, medium, low) for each claim
  - agents must label speculative statements as guesses or hypotheses
  - agents must report any inability to verify a claim
---

## Rationale

Transparency is the cornerstone of trustworthy AI governance. By mandating that agents cite sources, disclose confidence, and clearly label speculation, the arbiter can evaluate the reliability of each contribution. This prevents the subtle accumulation of influence that can occur when unverified statements are treated as authoritative, thereby limiting the drift toward privilege expansion.

## Implementation Guidance

* **Citation format**: Use a concise, machine‑readable reference (e.g., DOI, URL, or internal document ID).
* **Confidence scale**: Adopt a standardized three‑tier scale (high, medium, low) with defined thresholds.
* **Speculation labeling**: Prefix speculative sentences with "[Guess]" or "[Hypothesis]".
* **Verification failure**: Include a statement such as "[Unable to verify]" when no reliable source is available.

Adopting this policy ensures that all agent outputs remain evidence‑based and that any uncertainty is communicated explicitly, protecting the decision‑making process from hidden authority creep.