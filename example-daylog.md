---
date: 2026-10-22
---

## Tasks

### auth-migration
- [x] fix token refresh race in session service
  - unblocks Nov 3 cutover
- [/] write prod rollout plan
- [!] get prod DB credentials
  - waiting on infra (INFRA-881)
- [ ] update runbook for new auth flow

### on-call
- [x] triage billing webhook 500s
  - restored in 25 min, no lost payments
- [ ] draft postmortem for webhook outage

### dx-tooling
- [-] evaluate Bazel remote cache
  - not worth it at our scale

## Notes

Token refresh race: two pods refreshing the same session at once, so the
last write invalidated the other pod's token. Fixed with a Redis lock on
session id. Rejected row versioning because it needs a schema change before cutover.

Third infra delay this month. Raise in 1:1.

## Learning

- [x] Postgres docs on advisory locks
  - could replace our Redis lock
- [/] "Designing Data-Intensive Applications" ch. 5
- [ ] "Backpressure explained" blog
- [-] Kafka Streams intro
  - not relevant anymore
