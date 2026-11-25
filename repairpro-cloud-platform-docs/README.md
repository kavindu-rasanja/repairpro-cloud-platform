# RepairPRO Cloud Platform

**Commercial documentation repository** for RepairPRO — a Windows desktop repair-shop management product with centralized cloud services and multi-branch operations.

> **Repository status:** Documentation foundation / commercial planning. This repository does not contain the production application source code, credentials, customer data, or a verified production deployment.

**Product owner & developer:** Kavindu Rasanja  
**Initial target market:** Sri Lanka  
**Client platform:** Windows Desktop  
**Commercial model:** Lifetime licence (current product decision; licensing implementation and terms must be finalized before sale)

## Product direction

RepairPRO is designed to help mobile-device repair businesses manage repair jobs and connected shop operations through a Windows desktop application, with cloud-backed multi-branch coordination.

### Planned capability areas

- Repair tickets: customer and device registration, inspection, diagnosis, estimates, approval, repair status and completion.
- Customer records and repair history.
- Technician assignment and workload visibility.
- Parts and inventory, stock movements, purchases / GRN and barcode labels.
- POS, payments, receipts and business reporting.
- Owner-level multi-branch visibility and centralized configuration.
- Cloud synchronization with explicit conflict and offline-recovery handling.
- SMS notifications through a configurable gateway integration.
- Print layouts for repair job sheets, tickets, invoices and labels.

Feature availability must be confirmed against the actual release build. This list describes product scope, not a claim that every capability is already production-ready.

## Repository map

| Path | Purpose |
|---|---|
| `docs/` | Product, architecture, data, operations and release documentation |
| `docs/decisions/` | Architecture decision records |
| `docs/runbooks/` | Operational procedures |
| `docs/templates/` | Reusable release and incident templates |
| `SECURITY.md` | Vulnerability reporting guidance |
| `CONTRIBUTING.md` | Documentation contribution rules |
| `CHANGELOG.md` | Release history |
| `LICENSE-PLACEHOLDER.md` | Proprietary licensing notice pending legal review |

## Start here

1. Read [Product Overview](docs/PRODUCT_OVERVIEW.md).
2. Review [System Architecture](docs/SYSTEM_ARCHITECTURE.md).
3. Read [Cloud Architecture](docs/CLOUD_ARCHITECTURE.md).
4. Review [Security](docs/SECURITY.md) and [Data Protection](docs/DATA_PROTECTION.md).
5. Follow the [Commercial Release Roadmap](docs/COMMERCIAL_RELEASE_ROADMAP.md).

## Important implementation boundary

The documents describe a proposed target architecture based on the current product direction. They are not proof that infrastructure, security controls, integrations, backups, or compliance checks have already been implemented. Replace every `TBD` with verified implementation details before a public commercial launch.

## Security notice

Never commit `.env` files, Firebase service-account JSON, private keys, SMS gateway credentials, customer exports, database backups, signing certificates, or production logs. Use environment variables and a managed secrets store. See [Security](docs/SECURITY.md).

## Ownership

© 2026 Kavindu Rasanja. All rights reserved. Commercial distribution, redistribution, modification and use are subject to a separate written licence. See `LICENSE-PLACEHOLDER.md`.
