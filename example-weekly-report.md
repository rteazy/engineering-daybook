## Weekly update: Oct 19–23

**TL;DR:** Auth migration on track for Nov 3 cutover. Handled one billing incident.

**Done**
- auth-migration: fixed token refresh race in session service (unblocks Nov 3 cutover)
- auth-migration: load test passed at 2× peak
- on-call: triaged billing webhook 500s (restored in 25 min, no lost payments)

**In progress**
- auth-migration: write prod rollout plan (open 8 days)
- on-call: draft postmortem for webhook outage (open 2 days)

**Blocked**
- auth-migration: prod DB credentials, waiting on infra (INFRA-881), since Oct 20

**Dropped**
- dx-tooling: Bazel remote cache eval (not worth it at our scale)
