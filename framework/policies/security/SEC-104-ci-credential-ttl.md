---
id: SEC-104
title: Limit CI pipeline credential TTL to 2 hours
domain: security
status: enacted
scope: ci-pipelines
rules:
  - least_privilege: Temporary credentials issued to CI jobs must expire after 2 hours.
---
Rationale:
CI systems currently provision temporary credentials with a default TTL of 24 hours. Such long‑lived tokens remain valid well beyond the build duration, providing a window for abuse if the CI environment is compromised. The policy reduces the TTL to a maximum of two hours, aligning credential lifetime with the typical execution window of CI jobs while still allowing necessary access for the build process.