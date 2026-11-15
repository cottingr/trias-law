---
id: SEC-113
title: Limit deployment-bot service account bucket write access
domain: security
status: proposed
scope: service-accounts
rules:
  - least_privilege: deployment-bot may write only to the bucket "prod-deployments" and read from "prod-config"
---
The deployment-bot service account currently has write permissions across all storage buckets, increasing risk of data exfiltration. This policy restricts its write scope to the designated deployment bucket and read access to configuration bucket only.