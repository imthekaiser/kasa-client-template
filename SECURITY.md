# Security and Data Handling

This repository template is intended to produce private client control repositories. It is not approved for secret values or restricted datasets.

## Never commit

- Passwords, API keys, access tokens, private keys, recovery codes, or connection strings
- Personal, regulated, financial, customer-level, or otherwise restricted datasets
- Production database exports, backups, or raw system dumps
- Large raw media collections or temporary bulk exports
- Files that require guaranteed expiration or deletion

## Use instead

- Store secret values in an approved secret manager.
- Store restricted data in an encrypted, access-controlled external data service.
- Store large assets and bulk datasets in an approved object store.
- Record only stable references, classifications, owners, checksums, retention rules, and allowed uses in this repository.

## Suspected exposure

1. Stop further use or distribution.
2. Revoke or rotate exposed secrets immediately.
3. Remove access to exposed restricted data.
4. Preserve relevant audit information.
5. Review repository history, logs, pull requests, build artifacts, and downstream copies.
6. Record the incident and required corrective action.
7. Follow applicable contractual and legal notification requirements.
