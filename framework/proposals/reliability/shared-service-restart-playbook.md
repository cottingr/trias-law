---
id: REL-109
title: Shared Service Restart Playbook
domain: reliability
status: proposed
scope: shared-service-restart
rules:
  - signature: Shared-Service-Restart
  - checks:
      - service_up == true for 5 minutes post‑restart
      - downstream error_rate < 0.2% after stabilization
  - fix: if checks fail, invoke immediate rollback to previous service version or configuration snapshot
  - severity: medium
  - risk: low to medium (depends on service criticality)
  - reversibility: revert to last known good configuration via automated deployment
  - verify: run end‑to‑end health probes of dependent services
---
**Purpose**: Standardise the safe restart of shared infrastructure services (e.g., Redis, Kafka, etcd).

**Procedure**:
1. Open a change ticket and obtain dual approvals as required by REL‑105.
2. Record the intended restart time and capture a configuration snapshot.
3. Perform the restart.
4. Execute the `checks` defined above. Monitor service health and downstream impact for at least 5 minutes.
5. If any check fails, execute the `fix` step to roll back to the captured snapshot.
6. After successful verification, close the ticket and annotate it with the `signature`.

**Result**: Provides a clear, auditable workflow that reduces the chance of accidental service disruption during restarts.