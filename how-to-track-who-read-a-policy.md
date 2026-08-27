---
title: How to track who has read a policy in Confluence
---

# How to track who has read a policy in Confluence

You published the security policy. Six weeks later an auditor asks who has read it, and the
honest answer is "we sent an email". This page covers what Confluence gives you out of the box,
where it stops, and what to do about the gap.

## What Confluence can do on its own

**Page views.** Confluence Premium shows view counts and, in the analytics byline, who viewed a
page. That answers "did anyone open it" — not "did they read and accept it". A view is not a
confirmation, and it is not tied to a version.

**Inline comments or a table.** The low-tech version: ask everyone to add a row with their name
and the date, or comment "read". It works for ten people. At a hundred it becomes a page nobody
maintains, with no way to tell who is missing, and it silently keeps counting after the policy
changes.

**Labels + CQL.** Labels are searchable (`label = "policy"`), which is useful for finding
policies but says nothing about who read them.

## The three things that make an acknowledgement worth keeping

1. **It is tied to a version.** A confirmation against version 3 is not evidence that anyone read
   version 7. When the page changes, the round has to start over.
2. **It expires.** A signature from fourteen months ago proves nothing about this year's policy.
   Annual re-acknowledgement is the norm in ISO 27001 and SOC 2 programmes.
3. **It is visible where people work.** A report only an admin opens does not chase anyone; the
   ask has to sit on the page itself, and the state has to be searchable.

## Doing it with Ackdesk

[Ackdesk](../) adds those three to Confluence:

1. Open the page, click **Acknowledge** in the byline, and choose who has to read it — everyone,
   a group, or named people.
2. Each reader sees one button. The signature records the person, the timestamp and the page
   version.
3. Edit the page and the round reopens automatically, with the signatures cleared.
4. Set a re-read period per space; a daily sweep reopens rounds when it lapses.
5. Search `label = "ack-outstanding"` to list every page still waiting, or open the report for
   overall coverage, the spaces that are behind, and each person's own reading list.

It runs entirely on Atlassian Forge with no external calls, so the acknowledgement records never
leave your site — which is usually the first question a security review asks.

## What to write in the policy page itself

Two sentences save a lot of chasing: what the reader is confirming, and what happens if they do
not. "By acknowledging you confirm you have read and understood this policy and agree to follow
it. Outstanding acknowledgements are reported to your manager after seven days."

---

[Ackdesk for Confluence](../) · DataForte AB · hello@dataforteab.com
