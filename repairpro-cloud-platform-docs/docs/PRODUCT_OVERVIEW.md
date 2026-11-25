# Product Overview

## 1. Product definition

RepairPRO is a commercial Windows desktop application for mobile-device repair shops. It combines repair workflow management with shop operations and a cloud layer intended to coordinate multiple branches under an owner-controlled account.

## 2. Target users

- **Owner:** oversees branches, business performance, access and centrally managed settings.
- **Branch manager:** supervises branch operations, staff and daily activity.
- **Front-desk staff:** registers customers/devices, creates tickets, records estimates and payments.
- **Technician:** reviews assigned jobs, records diagnosis, parts and repair progress.
- **Inventory / cashier staff:** handles stock, purchases, sales and payment workflows.

Roles and permissions must be configured according to the actual release implementation.

## 3. Core workflows

### Repair lifecycle

1. Register or find a customer.
2. Register device details and received accessories.
3. Create a repair ticket and record the reported fault.
4. Inspect and diagnose the device.
5. Prepare an estimate and obtain customer approval or rejection.
6. Assign a technician and record repair progress.
7. Record parts and labour.
8. Complete quality checks and notify the customer.
9. Collect payment, print required documents and close the job.

### Shop operations

- Inventory item creation and stock tracking.
- Purchase / goods received note workflow.
- POS sales and payment recording.
- Barcode and ticket-label printing.
- Business reports and branch-level summaries.

### Multi-branch workflow

- Owner creates or authorizes a branch.
- Branch users authenticate and access only permitted branch data.
- Branch transactions are associated with a stable branch identifier.
- Owner dashboards aggregate authorized branch data.
- Shared settings are centrally administered where supported.
- Offline changes are synchronized after connectivity returns, subject to conflict rules.

## 4. Product principles

- Windows desktop is the committed client platform for the current commercial release.
- Offline operation is a product requirement; exact offline feature coverage must be documented and tested.
- Cloud synchronization must not silently overwrite conflicting business records.
- Branch data must be isolated by authorization rules, not merely by UI filtering.
- No AI features are in the current product scope.
- Keep daily workflows clear for non-technical shop staff.

## 5. Release status vocabulary

Use these labels in all documentation:

- **Implemented:** verified in the tagged build and covered by tests.
- **In progress:** actively being implemented.
- **Planned:** approved scope but not yet implemented.
- **Not supported:** explicitly outside product scope.
- **TBD:** decision or evidence is missing.

Do not label a feature “production-ready” without test evidence and operational readiness.
