# Multi-Branch System

## 1. Operating model

One tenant represents one repair business. The tenant owner can manage authorized branches. Each branch has its own operational users and records, while permitted owner views can aggregate branch performance.

## 2. Access model

| Role | Typical access |
|---|---|
| Owner | All branches in the tenant; user and central configuration management |
| Branch manager | Assigned branch operations and reports |
| Front desk | Customer, device, ticket and payment workflows permitted by policy |
| Technician | Assigned repair jobs and permitted repair updates |
| Inventory staff | Stock, purchase and movement workflows |
| Cashier | POS and payment workflows |

This is a recommended role model. Final permissions must match the implemented authorization rules.

## 3. Required safeguards

- Every request is authenticated.
- Tenant membership is checked server-side.
- Branch access is checked for every branch-scoped record.
- Cross-tenant access is denied by default.
- Owner access is restricted to the owner's tenant.
- Administrative changes are audited.
- User removal and branch deactivation revoke access promptly.
- Reports aggregate only records the requesting user may access.

## 4. Central configuration

For owner-managed SMS settings and other shared settings:
1. Owner edits configuration in a protected owner interface.
2. Server validates and stores a new configuration version.
3. Branch clients receive the new version through an authorized channel.
4. Clients acknowledge adoption.
5. Secrets remain server-side; clients receive only non-secret status or safe configuration.

Do not distribute provider passwords or API tokens to branch desktop applications.

## 5. Branch onboarding checklist

- Create tenant and owner identity.
- Create branch record and unique branch code.
- Invite users and assign least-privilege roles.
- Verify branch-scoped reads and writes.
- Verify owner-only cross-branch reports.
- Test offline operation and synchronization.
- Test revoked-user behavior.
- Confirm backup and audit coverage.
