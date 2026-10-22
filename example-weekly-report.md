## Weekly update: Oct 19–23

**Wins**
- auth-migration: unblocked Nov 3 cutover by fixing the token refresh race
- on-call: restored billing webhooks in 25 min with no lost payments

**Done**
- auth-migration: fixed token refresh race in session service
- auth-migration: load test passed at 2× peak
- on-call: triaged billing webhook 500s

**In progress**
- auth-migration: write prod rollout plan (open 8 days)
- on-call: draft postmortem for webhook outage (open 2 days)

**Blocked**
- auth-migration: prod DB credentials, waiting on infra (INFRA-881), since Oct 20

**Dropped**
- dx-tooling: Bazel remote cache eval (not worth it at our scale)
