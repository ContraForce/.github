# ContraForce `.github`

Org-wide defaults for every repository in the [ContraForce](https://github.com/ContraForce) organization.

## What lives here

| Path | Applies to | Inherited? |
| - | - | - |
| `profile/README.md` | The org landing page at `github.com/ContraForce` | n/a |
| `SECURITY.md` | Vulnerability disclosure policy | Yes |
| `CONTRIBUTING.md` | Branch, commit, and PR conventions | Yes |
| `SUPPORT.md` | Where customers and partners get help | Yes |
| `CODE_OF_CONDUCT.md` | Contributor Covenant 2.1 | Yes |
| `PULL_REQUEST_TEMPLATE.md` | Default PR body | Yes |
| `ISSUE_TEMPLATE/config.yml` | Routes issue reporters to Jira and support | Yes |

"Inherited" means a repo with no file of its own at that path automatically uses the one here.
A repo that defines its own copy always wins.

## What does not inherit

GitHub does not propagate these from an org `.github` repo, no matter where you put them:

- `CODEOWNERS` — must live in each repo
- `dependabot.yml` — must live in each repo
- Workflows — a workflow here runs *here*. To share CI, publish a reusable workflow
  (`on: workflow_call`) and call it from each repo.
- `LICENSE`

## Visibility caveat

Default community health files in a **non-public** `.github` repo do not apply to
**public** repos. This repo is currently internal, so `ContraForce/Azure-Sentinel` and
`ContraForce/integrations-examples` inherit nothing from it and need their own copies of
`SECURITY.md` and `CODE_OF_CONDUCT.md` until this repo is made public.

The member-facing org profile lives in the separate `ContraForce/.github-private` repo.
