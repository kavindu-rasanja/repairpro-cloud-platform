# ADR-0002: Documentation-First Repository

- **Status:** Accepted
- **Date:** 2026-11-25

## Context

The commercial cloud platform needs a clear source of truth before application source code is consolidated into a single repository.

## Decision

Create a private documentation-first repository named `repairpro-cloud-platform`. This initial repository contains product, architecture, security, data, operations and release documentation. It does not claim to contain the application source.

## Consequences

- Source code can be added later after repository and architecture review.
- Proposed architecture must be labeled as proposed until verified.
- Secrets and customer data are prohibited.
- Documentation changes should be reviewed and versioned.
