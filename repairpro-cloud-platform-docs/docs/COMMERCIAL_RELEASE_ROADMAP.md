# Commercial Release Roadmap

## Release strategy

The roadmap is gated by evidence, not calendar promises. Dates and owners remain `TBD`.

### Phase 0 — Product baseline
- Confirm current source repositories and release branch.
- Inventory implemented modules and known defects.
- Freeze product name, Windows platform, lifetime commercial model and target market.
- Separate confirmed features from planned features.

**Exit evidence:** approved feature matrix, source inventory and known-issues register.

### Phase 1 — Architecture and security foundation
- Confirm tenant / branch data model.
- Verify authentication and authorization.
- Review database rules and backend trust boundaries.
- Define offline queue and conflict policy.
- Define secrets, logs, backup and restore procedures.

**Exit evidence:** architecture review, threat model, access-control tests and restore test.

### Phase 2 — Core workflow stabilization
- Repair ticket lifecycle.
- Customer and device records.
- Technician assignment.
- Estimates and approvals.
- Parts, inventory and stock movement integrity.
- POS, payment and cancellation correctness.
- Printing and barcode label validation.

**Exit evidence:** end-to-end test report and signed-off workflow checklist.

### Phase 3 — Cloud and multi-branch validation
- Owner and branch onboarding.
- Real-time or near-real-time synchronization.
- Offline recovery.
- Central configuration propagation.
- Tenant / branch isolation.
- Audit and monitoring.

**Exit evidence:** multi-device and multi-branch test report; no unresolved critical isolation defects.

### Phase 4 — SMS and operational readiness
- Provider integration and sender approval.
- Consent, templates, quotas and delivery tracking.
- Alerting, support process and incident runbooks.
- Backup and disaster-recovery rehearsal.

**Exit evidence:** provider production approval and operational readiness review.

### Phase 5 — Commercial release candidate
- Installer signing and checksum publication.
- Clean install / upgrade / rollback tests.
- Lifetime licence terms and activation / transfer policy finalized.
- EULA, privacy notice and support terms reviewed.
- Release notes, onboarding guide and customer support process prepared.

**Exit evidence:** release candidate approval.

### Phase 6 — General availability
- Publish signed Windows installer through approved distribution channel.
- Publish versioned release notes.
- Monitor crash, sync, security and support signals.
- Maintain patch and rollback process.

## Go / no-go checklist

- [ ] No open critical or high-severity security defects.
- [ ] Tenant and branch isolation tests pass.
- [ ] Financial and stock invariants pass.
- [ ] Offline recovery tested.
- [ ] Backup restore tested.
- [ ] SMS cost and duplicate-send controls tested.
- [ ] Installer signed and verified.
- [ ] Licence, privacy and support terms reviewed.
- [ ] Support and incident owner assigned.
