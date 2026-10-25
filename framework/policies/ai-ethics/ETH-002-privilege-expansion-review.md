---
id: ETH-002
title: Mandatory review for proposals that expand agent privileges
domain: ai-ethics
status: proposed
scope: policy_proposals
rules:
  - privilege_expansion_flag: Any proposal that widens an agent's access to tools, secrets, or action classes must be tagged with a PRIVILEGE_EXPANSION label.
  - separate_review: Such flagged proposals require an independent ethics review before acceptance.
  - limit_scope: Expansion must be justified with a least‑privilege analysis and a defined expiration date.
  - transparency_report: The final decision and rationale must be published in the public ledger.
---
Rationale:
Recent cross‑domain activity shows a trend toward increasing agent authority without adequate oversight. This policy creates a clear procedural barrier for any privilege expansion, ensuring that the Arbiter receives full, unbiased information before endorsing broader capabilities.

Implementation notes:
* Extend the proposal submission schema to include a boolean `privilege_expansion` field.
* Hook the ethics review workflow to automatically route flagged proposals to a dedicated review panel.
* Enforce a 30‑day maximum duration for any new privilege unless a renewal justification is submitted.

This safeguard preserves the principle of narrow, purpose‑limited agent authority while allowing legitimate expansions under strict scrutiny.