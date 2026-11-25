# Cloud Architecture

## 1. Goals

- Support multiple branches under an owner-controlled business account.
- Synchronize authorized customers, devices, repair tickets, inventory and transactions.
- Provide centralized configuration where the product requires it.
- Support intermittent connectivity without losing acknowledged local work.
- Maintain tenant isolation and an auditable history.

## 2. Proposed service boundaries

| Service | Responsibility |
|---|---|
| Identity | User authentication, sessions and account lifecycle |
| Authorization | Tenant, branch and role permission checks |
| Business API | Validated repair, inventory, POS and finance operations |
| Data store | Durable cloud records and indexes |
| Sync coordinator | Change cursor, idempotency, retry and conflict workflow |
| Configuration | Owner-controlled settings and version distribution |
| Notification adapter | Provider-independent SMS requests and delivery status |
| Audit | Security-sensitive and financial event history |

Technology choices must be verified against the deployed system. Firebase is part of the current project direction, but exact Firebase products, regions, indexes, rules and functions are `TBD` until checked in the implementation.

## 3. Multi-tenant model

Recommended hierarchy:

```text
Platform
└── Tenant (one repair business)
    ├── Owner account
    ├── Branch A
    │   ├── Users
    │   ├── Customers
    │   ├── Repair tickets
    │   └── Inventory / transactions
    └── Branch B
        ├── Users
        ├── Customers
        ├── Repair tickets
        └── Inventory / transactions
```

A tenant may own multiple branches. A user may have access to one or more branches only through explicit membership records.

## 4. Synchronization contract

Each syncable mutation should carry:
- globally unique operation ID;
- tenant and branch scope;
- entity type and entity ID;
- operation type;
- schema version;
- client-generated timestamp (informational only);
- server-issued timestamp on acceptance;
- actor identity;
- base version / revision;
- payload or secure reference to payload.

Server requirements:
1. Authenticate and authorize the actor.
2. Validate tenant and branch membership.
3. Check idempotency key before applying.
4. Validate schema and business invariants.
5. Apply transactionally where supported.
6. Record resulting revision and audit event.
7. Return accepted, rejected or conflict status.

## 5. Conflict policy

| Data type | Recommended handling |
|---|---|
| Customer contact details | Field-aware merge or user review |
| Repair status | Validated state transition; reject stale invalid transitions |
| Payments | Append-only transaction records; never overwrite silently |
| Stock movements | Append-only ledger; reconcile quantities |
| Inventory description | Version check and manual conflict resolution |
| Central settings | Owner version wins only after explicit publish and client acknowledgement |

Do not use device clocks as the authority for conflict ordering.

## 6. Offline mode

Document offline capability per workflow. Local persistence should be encrypted where feasible and protected by the Windows user account. Clearly distinguish:
- saved locally;
- waiting to sync;
- synchronized;
- conflict needs attention;
- sync failed.

A local save must not be presented as a cloud-confirmed save. Define retention, retry backoff, queue limits and recovery behavior.

## 7. Availability and recovery

Before commercial launch, define service objectives:
- availability target: `TBD`;
- recovery time objective (RTO): `TBD`;
- recovery point objective (RPO): `TBD`;
- backup frequency and retention: `TBD`;
- restore test cadence: `TBD`;
- incident communication owner: `TBD`.
