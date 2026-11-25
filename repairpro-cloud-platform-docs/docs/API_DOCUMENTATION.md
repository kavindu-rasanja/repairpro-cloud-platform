# API Documentation

## Status

The exact production API contract is not yet verified in this documentation repository. Do not invent endpoint URLs or publish guessed request/response examples as live API behavior.

## Contract requirements

Every authenticated request should define:
- HTTP method and route;
- required role and tenant / branch scope;
- request schema and validation;
- success response schema;
- error codes and retryability;
- idempotency behavior;
- pagination and filtering;
- audit requirements;
- rate limits.

## Suggested resource groups

| Resource group | Typical operations |
|---|---|
| Identity | session, profile, membership |
| Tenants / branches | list, create, update, deactivate |
| Customers / devices | create, read, update, archive |
| Repair tickets | create, estimate, approve, assign, transition, close |
| Inventory | items, stock movements, GRN |
| POS | sales, payments, refunds |
| Reports | branch and owner summaries |
| Configuration | read safe config, owner update |
| Notifications | enqueue, status, templates |
| Sync | push operations, pull changes, resolve conflicts |

## Error model

Use stable machine-readable codes such as:
- `UNAUTHENTICATED`
- `PERMISSION_DENIED`
- `TENANT_SCOPE_MISMATCH`
- `BRANCH_SCOPE_MISMATCH`
- `VALIDATION_FAILED`
- `REVISION_CONFLICT`
- `IDEMPOTENCY_REPLAY`
- `RATE_LIMITED`
- `SERVICE_UNAVAILABLE`

These are proposed names. Align them with the actual implementation before publishing a stable API contract.
