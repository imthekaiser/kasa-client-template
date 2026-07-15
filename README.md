# KASA Client Repository Template

Template for `client-{client_id}` — the single private source of truth for
one client engagement. Humans and agents read this repo during builds;
everything they need is either in it or listed in `client.yaml` under
`external_storage`.

## Layout

| Path | What lives there |
|---|---|
| `client.yaml` | Client facts: identity, approver, repos, external storage, secret names |
| `goals.yaml` | Business goals for the engagement |
| `tasks/` | One YAML per scoped agent task |
| `intake/` | Questionnaire, responses, and client-provided documents |
| `brand/` | Brand guide plus web-ready logos, icons, and photos |
| `website/` | Site config (`site.yaml`) and one markdown file per page |
| `data/` | Small working datasets (CSV/JSON) for analysis |
| `notes/` | Meeting notes and the running decision log |

Add folders only when the engagement needs them.

## Setup

1. Create a new **private** repo named `client-{client_id}` from this template.
2. Fill in `client.yaml` and `goals.yaml`.
3. Run the intake: record answers in `intake/responses.md`, drop provided
   files into `intake/documents/`.
4. Add brand assets and draft website pages as the engagement progresses.

## The five rules

1. **Private.** This repo is confidential by default. Never make it public.
2. **No secrets in Git.** Reference secrets by name in `client.yaml`; values
   live only in the deploy platform or secret manager.
3. **No sensitive or bulk data in Git.** Personal, financial, customer-level,
   or regulated data — and files over 10 MB — go to external storage, with
   one line in `client.yaml` → `external_storage`. Git history is permanent,
   so nothing that may need guaranteed deletion goes in it.
4. **Approval is a status field.** Public output is built only from files
   with `status: approved`, and only the approver named in `client.yaml`
   flips a status to `approved`, via pull request. The merged PR is the
   approval record.
5. **One source of truth.** Don't restate a fact in two files; link to where
   it lives. Output repos (like the website) receive copies, never originals.

Full policy: `docs/data-management.md` in the `kasa-platform` repo.
