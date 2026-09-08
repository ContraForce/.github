# Contributing

These are the org-wide defaults for ContraForce repositories. A repo with its own
`CONTRIBUTING.md` overrides this one; anything not contradicted there still applies.

## Work tracking

Jira at [contraops.atlassian.net](https://contraops.atlassian.net) is the source of
truth for work, not GitHub issues.

| Project | Purpose | Referenced from code? |
| - | - | - |
| `PLAT` | Work tracking — the ticket the change delivers | **Always.** Every branch, commit, and PR carries a `PLAT` key |
| `CC` | Change control records | Sometimes, on production releases. Never as the primary key |
| `FR` | Idea and feature-request intake | **Never.** `FR` items are groomed into `PLAT` tickets; reference the `PLAT` key, not the `FR` one |

If there is no `PLAT` ticket for the work you are about to do, create one first. An `FR`
item is not a substitute — it has to become a `PLAT` ticket before work starts.

## Branches

```
<type>/PLAT-<number>-<short-slug>
```

| Type | Use for |
| - | - |
| `feature/` | New capability |
| `fix/` | Bug fix |
| `hotfix/` | Urgent production fix |
| `chore/` | Tooling, dependencies, housekeeping |

Example: `feature/PLAT-2559-add-grip-handle`

The `PLAT` key must appear in the branch name — tooling parses it with `PLAT-\d+` to
derive commit prefixes and PR titles.

## Commits

```
PLAT-XXXX: Capitalized imperative summary (type)

Body explaining what the problem was and why this change addresses it.

- Specific change
- Specific change
- Reference: PLAT-XXXX
```

Rules:

- The subject starts with the `PLAT` key, then a colon and a space
- After the prefix, start with a capitalized imperative verb: `Add`, `Fix`, `Update`
- Keep the whole subject under 72 characters
- Optionally suffix a conventional type in parentheses: `(feat)`, `(fix)`, `(refactor)`,
  `(test)`, `(docs)`, `(style)`, `(perf)`, `(ci)`, `(chore)`
- The body explains the *why*, not a restatement of the diff

Examples:

```
PLAT-2559: Add envelope encryption for customer secrets (feat)
PLAT-2601: Fix null reference in agent status update (fix)
```

Do not pass `--no-verify` unless you are changing `.pre-commit-config.yaml` and
deliberately not committing that change.

## Pull requests

Two flows:

- **Development** — feature branch → `dev`
- **Release** — `dev` → `main`

Before opening a PR:

1. Rebase or merge the latest `dev`
2. Build and run the tests that cover what you touched
3. Self-review the diff for secrets, auth changes, unvalidated input, and new
   external dependencies
4. Fill in the PR template, including the `PLAT` link

PR titles follow `PLAT-XXXX: Descriptive Title`.

Keep PRs scoped to one ticket. If you find an unrelated problem, file a ticket rather
than widening the change.

Production releases (`dev` → `main`) also update the corresponding `CC` change-control
record after the deploy succeeds. Link the `CC` key in the release PR when one applies.

## Reviews

- At least one approval before merge
- Required checks must pass; do not merge around a red build
- Resolve review threads rather than silently force-pushing over them
- The author merges once approved, unless the repo says otherwise

## Code owners

`CODEOWNERS` is not inheritable from this repository — GitHub only reads it from the
repo it applies to. Each repo that needs review routing must define its own at
`.github/CODEOWNERS`.

## Security

Never commit credentials, tokens, connection strings, or customer data. If you believe
you have found a vulnerability, follow [SECURITY.md](SECURITY.md) — do not open a
public issue.

## Notes on specific repositories

- **`platform`** also mirrors refs from Azure DevOps via the `azdo-sync` workflow.
  Check with the team before assuming a branch there originated on GitHub.
