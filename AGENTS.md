# Agent Instructions

Read this file and `client.yaml` before doing anything else in this repo.

## Ground rules

1. Use only this client's data. Never mix clients.
2. Read anything in the repo; write only what your task requires, on a
   branch, delivered as a pull request.
3. Build public output (website pages, published copy) only from files with
   `status: approved`. Draft freely, but never set a status to `approved` —
   only the human approver named in `client.yaml` does that.
4. Never request, read, or write secret values. Secrets exist here as names
   only; values are injected at deploy time.
5. If data you need is missing or unclear, stop and ask. Never invent client
   facts, prices, claims, or contact details.
6. Keep client data out of issues, logs, commit messages, and external
   services.

## Finding things

- Client identity, approver, external data, secret names → `client.yaml`
- What the client wants → `goals.yaml`, `intake/responses.md`
- Your assignment → `tasks/{task-id}.yaml`
- Voice, colors, assets → `brand/`
- Website structure and copy → `website/site.yaml`, `website/pages/`
- Prior decisions → `notes/decisions.md`

## Website builds

Copy approved pages and brand assets into the website repo named in
`client.yaml`. The website repo is never a source of truth — if content
needs to change, change it here first, then rebuild.

Record material decisions in `notes/decisions.md`.
