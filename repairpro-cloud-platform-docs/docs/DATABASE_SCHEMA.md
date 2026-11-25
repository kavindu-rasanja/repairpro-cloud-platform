# Database Schema (Logical Proposal)

This document defines a logical model. It is not a statement of the current deployed Firebase schema.

## 1. Common fields

Most mutable business entities should include:
- `id`: immutable unique identifier;
- `tenantId`: owning business;
- `branchId`: owning branch where applicable;
- `createdAt`, `createdBy`;
- `updatedAt`, `updatedBy`;
- `revision`: monotonic server-managed version;
- `schemaVersion`: data format version;
- `archivedAt` or explicit lifecycle state where soft deletion is required.

Never rely on a client-supplied tenant or branch value without server-side authorization.

## 2. Core entities

| Entity | Important fields |
|---|---|
| Tenant | name, status, ownerUserIds, plan / licence state |
| Branch | tenantId, name, address, contact details, status |
| User | identity provider UID, display name, status |
| Membership | userId, tenantId, branchIds, role, permissions |
| Customer | name, phone, alternate contact, notes |
| Device | customerId, brand, model, colour, serial / IMEI if collected |
| RepairTicket | ticketNo, customerId, deviceId, reportedFault, diagnosis, status, assignedTechnicianId |
| TicketPart | ticketId, inventoryItemId, quantity, costSnapshot, sellingPriceSnapshot |
| Estimate | ticketId, labour, parts, discount, total, approval state |
| Payment | reference, ticketId / saleId, amount, method, recordedAt |
| InventoryItem | SKU, barcode, name, cost, selling price, reorder level |
| StockMovement | itemId, movementType, quantity, reference, actor |
| Purchase / GRN | supplier reference, lines, quantities, costs |
| Sale | invoiceNo, branchId, lines, totals, status |
| SmsMessage | recipient, templateId, provider, status, providerReference |
| AuditEvent | actor, action, entity, entityId, timestamp, metadata |
| SyncOperation | operationId, entity, revision, status, retry metadata |

## 3. Financial and stock integrity

- Store money using integer minor units (e.g. cents) or a carefully defined decimal representation; never use binary floating point for authoritative financial calculations.
- Preserve cost and selling-price snapshots on historical ticket and sale lines.
- Record payments as immutable ledger entries; corrections should be compensating entries with audit trails.
- Record stock changes as movements. Do not rely only on a manually editable quantity field.
- Define rounding, discounts, taxes (if applicable), refunds and cancellation rules before release.

## 4. Deletion policy

Prefer archive / soft-delete for business records referenced by tickets, invoices, payments or audit events. Define retention and erasure procedures for personal data. Hard deletion must not break financial or operational history.

## 5. Indexes and constraints

`TBD`: document actual Firestore indexes, SQL constraints or equivalent query indexes from the deployed database. Add uniqueness rules for ticket numbers, invoice numbers and idempotency keys at the authoritative service layer.
