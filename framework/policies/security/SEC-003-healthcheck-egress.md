---
id: SEC-003
title: Limit Health‑Check Script Network Egress
domain: security
status: proposed
scope: network
rules:
  - least_privilege: Health‑check scripts may egress only to the configured health‑check endpoint IP/port.
  - deny_all: All other outbound traffic from the health‑check service is denied by default.
  - monitoring: Any attempt to reach non‑allowed destinations is logged and triggers an incident.
---
A dedicated security group is created for health‑check instances, restricting outbound rules to the single health endpoint. Future modifications require explicit policy amendment.
