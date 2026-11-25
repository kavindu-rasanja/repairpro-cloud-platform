# Security Policy

## Supported release

Security reports should identify the affected RepairPRO version, Windows version, reproduction steps and potential impact. Do not include real customer data or live credentials.

## Reporting

Until a dedicated private security contact is published, report vulnerabilities privately to the product owner through a verified contact channel. Do not publish exploit details or customer information in public issues.

## Mandatory controls before commercial release

- Enforce authentication and authorization server-side.
- Enforce tenant and branch isolation for every data operation.
- Apply least privilege to Firebase rules, service accounts and cloud roles.
- Keep secrets out of source code and desktop bundles.
- Use TLS for network traffic.
- Validate and normalize all untrusted input.
- Rate-limit authentication, sensitive APIs and SMS sends.
- Protect against replay and duplicate writes with idempotency.
- Audit permission changes, financial operations and administrative actions.
- Keep dependencies patched and scan builds for known vulnerabilities.
- Sign Windows installers and define update authenticity checks.
- Test backup restoration and incident response.

## Secret handling

Never commit:
- `.env`, `.env.*` (except a sanitized `.env.example`);
- Firebase service-account JSON or private keys;
- Cloudflare API tokens;
- SMS gateway usernames/passwords/API tokens;
- database exports or production backups;
- code-signing certificates and private keys;
- customer phone numbers, device identifiers or repair records.

If a secret is committed, revoke and rotate it immediately. Removing it from the latest commit is not sufficient.

## Vulnerability response

1. Acknowledge the report.
2. Reproduce in a non-production environment.
3. Assess severity, scope and affected versions.
4. Contain active exposure and rotate credentials if required.
5. Prepare and test a fix.
6. Release a patched build and communicate upgrade steps.
7. Record lessons learned without exposing sensitive details.
