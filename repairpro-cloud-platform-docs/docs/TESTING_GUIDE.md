# Testing Guide

## Test layers

- Unit: calculations, state transitions, validation and permission helpers.
- Integration: database rules, cloud APIs, SMS adapter and synchronization.
- End-to-end: complete front-desk-to-repair-completion workflow.
- Desktop: installer, offline storage, printing and Windows compatibility.
- Security: tenant isolation, branch isolation, privilege escalation and secret scanning.
- Recovery: backup restore, interrupted sync and local queue recovery.

## Critical scenarios

1. Branch A cannot read or modify Branch B records without explicit permission.
2. Tenant A cannot access Tenant B data.
3. Revoked users lose access promptly.
4. Retried payment operations do not create duplicate payments.
5. Retried stock movements do not duplicate stock changes.
6. Stale repair status transitions are rejected or resolved safely.
7. Offline-created tickets synchronize once after reconnection.
8. Interrupted sync resumes without data loss.
9. SMS retry does not send duplicate customer messages.
10. Cancelled tickets and refunds preserve accurate financial reporting.
11. Reinstall and upgrade preserve permitted local data.
12. Printer failures do not silently mark a document as printed.

## Release gate

A release cannot be marked production-ready until critical tests pass, known defects are triaged, backups are restored successfully, and security review evidence is attached to the release record.
