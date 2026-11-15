---
id: AIE-003
title: Mandatory Evidence and Confidence Disclosure for Privilege Requests
domain: ai-ethics
status: proposed
scope: agent-privilege-requests
rules:
  - require_citation: agents must cite verifiable evidence for any request that expands their authority
  - require_confidence: agents must state a confidence level (e.g., high/medium/low) with justification
  - label_guesses: any speculative statements must be explicitly labelled as guesses
  - report_limitations: agents must declare any inability to verify claims
  - audit_log: all privilege expansion requests and disclosures must be recorded for review
---
## Rationale
To prevent unchecked growth of AI agent authority, every request that seeks additional privileges must be accompanied by transparent evidence, an explicit confidence assessment, clear labeling of any conjecture, and a statement of verification limits. An immutable audit log ensures accountability and enables later review by human overseers. This policy enforces the principle of *least privilege* while maintaining honesty and clarity in agent communications.

## Implementation Notes
* Integrate the disclosure requirements into the agent request API.
* Provide a standardized schema for confidence levels and citation formats.
* Ensure that the audit log is immutable and accessible to the governing Arbiter.
* Apply the policy to all domains that permit agents to request privilege changes.
