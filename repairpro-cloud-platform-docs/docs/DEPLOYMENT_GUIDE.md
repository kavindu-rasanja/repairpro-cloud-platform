# Deployment Guide

## Environments

Maintain separate development, staging and production environments. Each must have separate credentials, databases / projects, SMS settings and access policies.

## Windows desktop release

1. Verify source revision and dependency lockfile.
2. Run lint, unit, integration and security checks.
3. Build the renderer and Electron application.
4. Verify app identity, version, icons and installer metadata.
5. Test clean installation, upgrade, uninstall and reinstall.
6. Test local data migration and recovery.
7. Sign installer and executable with a protected code-signing certificate.
8. Test on supported Windows versions and realistic shop hardware.
9. Publish checksum and release notes.
10. Preserve rollback instructions and previous supported installer.

## Cloud deployment

- Confirm hosting region and service account permissions.
- Apply database rules and indexes through reviewed deployment steps.
- Apply backend changes using versioned migrations.
- Configure secrets outside source control.
- Enable monitoring, error reporting and audit logs.
- Verify backups and restore procedure.
- Run tenant-isolation and branch-isolation tests.
- Perform a production smoke test with synthetic data.

## Rollback

Every release must specify:
- application rollback version;
- backend compatibility window;
- database migration rollback or forward-fix plan;
- configuration rollback;
- communication owner.

Never roll back a database schema blindly after newer clients have written data.
