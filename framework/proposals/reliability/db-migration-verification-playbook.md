---
id: REL-108
title: Database Migration Verification Playbook
domain: reliability
status: proposed
scope: database-migration
rules:
  - signature: DB-Migration-Verification
  - checks:
      - replication_lag < 5s
      - query_latency within 10% of baseline
      - error_rate < 0.1%
  - fix: execute automated rollback of schema version if any check fails
  - severity: high
  - risk: medium
  - reversibility: full rollback via versioned schema migration scripts
  - verify: re‑run health‑check suite after rollback to confirm baseline restored
---
**Purpose**: Provide a repeatable, auditable procedure for verifying that a database migration completed safely.

**Steps**:
1. After migration, run the health‑check suite defined in REL‑104.
2. Collect metrics for replication lag, query latency, and error rate.
3. Compare against thresholds defined under `checks`.
4. If any metric exceeds its threshold, trigger the `fix` step to roll back the migration using the stored versioned scripts.
5. After rollback, re‑run the health‑check suite (`verify`).
6. Document the outcome in the change‑log with the `signature`.

**Outcome**: Guarantees that migrations either succeed within defined safety bounds or are cleanly reverted, minimizing outage risk.