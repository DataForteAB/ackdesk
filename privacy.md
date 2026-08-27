---
title: Privacy Policy — Ackdesk for Confluence
---

# Privacy Policy

**DataForte AB** · Tant Gröns väg 54, 147 60 Uttran, Sweden
Contact: hello@dataforteab.com
Last updated: 22 August 2026

This policy describes how the Atlassian Marketplace app **Ackdesk for Confluence** ("the app")
handles data. The app is built on Atlassian Forge and runs on Atlassian's infrastructure.

## The short version

Ackdesk never leaves your Atlassian site. It has **no external egress at all** — no third-party
service, no analytics, no telemetry — which is why it qualifies for Atlassian's *Runs on Atlassian*
programme. Everything it stores lives in Forge storage inside your own tenant.

## What the app does with your data

Ackdesk records approvals on Confluence pages and mirrors the state onto a page label. It
processes:

- **Acknowledgements**: who confirmed they read a page, when, and which version they read.
- **Page identifiers and metadata**: the page id, its title, its space key and its version number,
  so an approval can be tied to the exact version of the page it was given for.
- **Account ids** of the people asked to review and of the person who asked, so the app can show
  who owes a decision. Names and avatars are rendered by Atlassian from those ids; the app does not
  store them.
- **Configuration you enter**: the quorum rule, default reviewers, the review-by period and the
  label prefix, per site and per space.

The app collects no analytics, does not profile users, and does not sell or share data with anyone.
DataForte AB has no access to your Confluence site.

## Where data is stored

All app data lives in the **Forge Key-Value Store**, inside Atlassian's cloud infrastructure,
scoped to your installation. Labels are written into Confluence itself, where they are ordinary
page labels visible to anyone who can see the page.

## Retention and deletion

Records live for as long as the app is installed. Uninstalling the app removes its Forge storage,
including every approval record and every setting. Labels already written to pages remain, because
they are Confluence content — remove them from the page if you no longer want them.

## Your rights

Under the GDPR, DataForte AB acts as a **data processor** for the data above; the Atlassian site
owner is the controller. Requests to access, correct or delete personal data should go to the site
owner, who can act on them directly in Confluence, or to hello@dataforteab.com.

## Changes

Material changes to this policy will be published on this page with a new date.
