---
title: Security Policy — Ackdesk for Confluence
---

# Security Policy

**DataForte AB** · Tant Gröns väg 54, 147 60 Uttran, Sweden
Security contact: hello@dataforteab.com (put "SECURITY" in the subject)
Last updated: 24 August 2026

This is the security policy for **Ackdesk for Confluence** ("the app"). It sits alongside the
[Privacy Policy](privacy.html), which describes what data the app handles; this page describes
how that data is protected.

## Architecture and hosting

The app is an **Atlassian Forge** app. It runs on Atlassian's own infrastructure inside the
customer's cloud site — DataForte AB operates no servers, no database and no network endpoints
of its own for this product.

The app makes **no external calls**. Its manifest declares no egress permissions, which
Atlassian enforces at the platform level: a request to any third-party host would be blocked by
Forge, not merely discouraged by us. This is what qualifies the app for Atlassian's
*Runs on Atlassian* programme.

## Data protection

- **What is stored:** the Atlassian account ids of people who acknowledged a page, the timestamp and page version of each acknowledgement, the page id, title and space key, cached group member counts, and the app's own configuration (audience, re-read period, label prefix). No page bodies, no attachments, no credentials.
- **Where:** the Forge Key-Value Store, inside Atlassian's infrastructure, scoped to the
  customer's own installation. Data from one customer site is never readable from another.
- **In transit:** all traffic is between Forge and Confluence over Atlassian's internal TLS-protected
  channels. The app opens no connections of its own.
- **At rest:** encryption at rest is provided by the Forge platform.
- **Retention:** app data lives as long as the app is installed. Uninstalling removes the app's
  Forge storage. There is no backup of customer data outside Atlassian, because there is no copy
  outside Atlassian.
- **Sub-processors:** none. Atlassian is the only processor involved.

## Access control

- No DataForte AB employee has access to customer content. We cannot read a customer's
  Confluence data: the app runs with the permissions granted at install time, and its storage is not
  exposed to us.
- Access to the Forge developer console and the Marketplace partner account is limited to named
  individuals, each protected by **two-factor authentication** on their Atlassian account.
- Source code lives in a private GitHub organisation with two-factor authentication required.
  Deployments to production are made from a reviewed commit by an authorised individual.

## Secure development

- Every behaviour change ships with automated tests; the pure logic of the app is unit-tested
  and CI runs lint plus the full test suite on every push and pull request.
- Dependencies are kept minimal (the Atlassian Forge SDK and React) and are reviewed on update;
  known-vulnerability advisories are checked with `npm audit` before a production deploy.
- Scope changes are deliberate: Forge treats a permission change as a major version, which an
  administrator must approve before it reaches their site.

## Vulnerability reporting

Report a suspected vulnerability to **hello@dataforteab.com** with "SECURITY" in the subject.
Please include the affected app, a description, and steps to reproduce.

- Acknowledgement within **two business days**.
- An initial assessment, including a severity rating, within **five business days**.
- Fixes for confirmed high-severity issues are deployed as soon as they are validated, and we
  keep the reporter informed until the issue is closed.

We do not run a paid bug bounty, and we will not take legal action against researchers who
report in good faith, avoid privacy violations and give us reasonable time to fix an issue.

## Incident response

DataForte AB maintains a written incident response plan. In summary:

1. **Detect and triage** — an alert, a customer report or a researcher report opens an incident;
   severity is assigned within one business day.
2. **Contain** — the affected app version is rolled back or disabled through the Forge developer
   console. Because the app holds no data outside Atlassian, containment does not depend on us
   securing external infrastructure.
3. **Notify** — affected customers are contacted at the email on their Marketplace subscription.
   Where a personal data breach is involved, notification follows GDPR Article 33: the relevant
   supervisory authority within **72 hours** of becoming aware.
4. **Remediate and review** — a fix is deployed, root cause is written up, and the resulting
   change is added to the test suite so the same fault cannot return silently.

## Business continuity

The app's availability is Atlassian's platform availability; there is no separate DataForte AB
service that can fail. Source code and deployment history are retained so any released version
can be rebuilt and redeployed.

## Compliance posture

- **GDPR:** DataForte AB acts as a data processor; the Atlassian site owner is the controller.
- The app holds no payment data, no credentials and no authentication secrets of the customer.
- We hold no SOC 2 or ISO 27001 certification today; the app's security posture rests on the
  Forge platform's controls and the practices described above. This page is updated when that
  changes.
