# Agent Instructions

## Start-up order

1. Read `client.yaml`.
2. Confirm the task scope, permitted source IDs, allowed outputs, and human approver.
3. Load only the smallest context set required for the task.
4. Stop when required data or authorization is missing; do not invent client facts.

## Canonical-source rules

- Treat `client.yaml` as the authoritative catalog for the engagement.
- Treat each referenced file or external location as canonical only for the data assigned to it.
- Do not duplicate structured facts across files when a stable source ID can be referenced.
- Preserve source IDs in material drafts and deliverables.
- Keep generated output separate from approved source material.

## Data access

- Default to read-only access.
- Access only data items permitted by the task contract or context pack.
- Do not access restricted data without explicit task-specific authorization.
- Prefer sanitized extracts over complete datasets.
- Do not place client data in issues, pull requests, logs, or external prompts unless specifically authorized.

## Secrets

- Never request, read, write, print, summarize, or commit secret values.
- Use only binding IDs from `references/secret-bindings.yaml`.
- Secret values must be supplied to authorized systems at runtime by an approved secret manager.

## Publication

- Default all client material to non-public.
- Do not copy material into a public or deployable repository unless its publication status is `approved_public`.
- Confirm that an approval record identifies the approver, approval time, and approved scope.
- Approval of one asset, page, or use does not approve unrelated material.

## Changes

- Make scoped changes through a branch and pull request unless a human explicitly authorizes another method.
- Do not overwrite client-provided source material with generated content.
- Record material decisions in `decisions/decision-log.yaml`.
- Update `client.yaml` when canonical locations, owners, lifecycle states, or context packs change.
