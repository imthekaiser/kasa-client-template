# KASA Client Repository Template

Canonical control-plane template for a private `client-{client_id}` repository.

This repository structure is designed to hold normal confidential engagement information, structured client facts, approved website content, decisions, manifests, and references to externally stored data. It is not a secret manager, restricted-data store, database backup location, or bulk-file archive.

## Use

1. Create a new **private** repository from this template using the name `client-{client_id}`.
2. Complete every required field in `client.yaml`.
3. Record goals, intake responses, structured content, decisions, and approvals in their canonical files.
4. Register every material source in `client.yaml` or the referenced catalog.
5. Give agents only the smallest context pack required for an approved task.
6. Copy content into a deployable repository only after it is explicitly approved for public use.

## Start here

- Human and AI workers start with `client.yaml`.
- Worker rules are in `AGENTS.md`.
- Secret binding names are recorded in `references/secret-bindings.yaml`; secret values are never stored here.
- Large or restricted files are recorded in `datasets/catalog.yaml` or `references/external-sources.yaml` and stored in an approved external system.

## Repository map

| Path | Purpose |
|---|---|
| `client.yaml` | Canonical client manifest and source index |
| `goals/` | Business goals and measurable outcomes |
| `intake/` | Intake questions, responses, and normal source documents |
| `content/` | Structured company, service, contact, and page content |
| `assets/` | Approved, reasonably sized working and web-ready assets |
| `datasets/` | Dataset catalog, schemas, and sanitized samples only |
| `decisions/` | Material engagement decisions and rationale |
| `approvals/` | Publication and delivery approvals |
| `deliverables/` | Final or client-review deliverables |
| `references/` | External source and secret-binding references |

## Data boundaries

Allowed in this repository:

- Goals, intake responses, meeting notes, and normal working documents
- Structured facts and draft content
- Approved public content and web-ready assets
- Dataset manifests, schemas, checksums, and sanitized samples
- Decisions, approval records, and acceptance criteria

Never store here:

- Passwords, access tokens, private keys, API keys, or connection strings
- Personal, regulated, financial, customer-level, or otherwise restricted datasets
- Production database exports or backups
- Large raw media libraries or frequently regenerated bulk exports
- Files requiring guaranteed expiration or deletion

## Publication rule

Only content or assets with `publication_status: approved_public` and a corresponding approval record may be copied into a public website build or public asset location.
