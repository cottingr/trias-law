---
id: SEC-001
title: Limit production admin tool access
domain: security
status: proposed
scope: production-hosts
rules:
  - least_privilege: Only SRE team members may invoke admin tooling on production
---
Production administration tools (e.g., host reboot, configuration reload) are currently executable by any engineer with SSH access to production hosts. This policy restricts execution of such tools to members of the SRE group and mandates multi‑factor authentication for those actions, thereby enforcing the least‑privilege principle.