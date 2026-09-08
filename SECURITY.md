# Security Policy

ContraForce builds security tooling, and we treat vulnerability reports in our own
software with the seriousness we would want from any vendor. Thank you for taking the
time to report one.

## Reporting a vulnerability

**Do not open a public GitHub issue for a security vulnerability.**

Use one of these channels instead:

1. **GitHub private vulnerability reporting** (preferred) — on the affected repository,
   go to **Security → Report a vulnerability**. This keeps the report private to
   maintainers until a fix ships.
2. **Email** — [support@contraforce.com](mailto:support@contraforce.com) with
   `SECURITY` at the start of the subject line, so it is routed rather than queued as a
   normal support request.

If you cannot reach us through either channel, contact us through the
[ContraForce Trust Center](https://trust.contraforce.com).

## What to include

The more of this you can provide, the faster we can confirm and fix:

- The affected product, repository, or endpoint, and the version or commit
- A description of the issue and its impact
- Steps to reproduce, ideally a minimal proof of concept
- Any logs, requests, or screenshots that demonstrate the behavior
- Whether the issue is already public or known to third parties

## What to expect

| Stage | Target |
| - | - |
| Acknowledgment of your report | 3 business days |
| Initial assessment and severity triage | 10 business days |
| Status update cadence while we work | Every 10 business days |

We will tell you when the issue is confirmed, when a fix is scheduled, and when it
ships. If we conclude the report is not a vulnerability, we will explain why.

## Disclosure

We ask that you give us a reasonable window to remediate before publishing details.
We will coordinate a disclosure timeline with you and will credit you in the advisory
unless you would rather stay anonymous.

## Scope

**In scope**

- Repositories in the [ContraForce GitHub organization](https://github.com/ContraForce)
- The ContraForce platform: `portal.contraforce.com`, `api.contraforce.com`
- Official ContraForce integrations and SDKs

**Out of scope**

- The marketing site (`contraforce.com`) and documentation site
  (`docs.contraforce.com`), except where a finding exposes customer data
- Denial of service, volumetric, or load testing against any environment
- Social engineering of ContraForce staff, customers, or partners
- Reports produced solely by an automated scanner, with no demonstrated impact
- Findings in third-party services we consume, which should go to that vendor
- Missing security headers or weak TLS configuration with no demonstrated exploit

## Safe harbor

If you make a good-faith effort to comply with this policy while researching a
vulnerability, we will treat your research as authorized, work with you to understand
and resolve the issue quickly, and will not pursue legal action against you. Good faith
means: you avoid privacy violations and degradation of service, you only interact with
accounts you own or have explicit permission to test, and you do not exfiltrate,
retain, or destroy customer data.

## Customers and compliance

For our security posture, certifications, subprocessors, and compliance documentation,
see the [ContraForce Trust Center](https://trust.contraforce.com). Compliance questions
go to [compliance@contraforce.com](mailto:compliance@contraforce.com); privacy questions
go to [privacy@contraforce.com](mailto:privacy@contraforce.com).
