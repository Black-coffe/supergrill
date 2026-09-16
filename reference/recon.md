# Reconnaissance — what to read before asking anything

The first rule of Supergrill: never ask what the environment can tell you. Recon runs before the first question and scales with the level.

## Tiers of sources

| Tier | Examples | Permission | Level |
|---|---|---|---|
| **Local** | the message, attachments, project files and code, docs, prior `grill/` briefs, memory or notes the agent keeps, glossaries | automatic | all |
| **Connected, read-only** | call or meeting archives, knowledge bases, document stores, analytics, CRM, ticket trackers, any read-only MCP-style source | automatic | deep, super |
| **Web** | search, documentation sites, registries, public filings | automatic for public topics; **ask once** when the topic contains private deal names, personal names, non-public plans, or anything the user would not want in a search log | deep, super |
| **Write / external actions** | posting, emailing, creating tickets, changing records | **never** during a grill | — |

The local overlay (`SUPERGRILL.local.md`) may list the user's connected sources by name and mark topics as confidential by default. Read it first.

## Confidentiality rule for the web

Before any web query, ask yourself: does the query string itself leak something? A company name in a private deal, a person's name, an unreleased product name, an internal codename. If yes, either strip the identifier from the query (search the category, not the name) or ask the user once: "Recon wants to search the web for `<terms>`. Allow, restrict to generic terms, or skip?" Record the answer in the brief and reuse it for the session.

## What recon produces

A private map, not a report (except in `super`, where Stage 0 ends with a visible recon report):

- **Answered already** — questions whose answers are in the sources. Do not ask them; state the answer and ask the user to confirm or correct only if it is load-bearing.
- **Contradictions in the sources** — two documents, a document and the code, a call and a spec. These jump the queue: they become the earliest D4 questions.
- **Traces** — things mentioned but not present: "the model" referenced in a call, a link to a spreadsheet that is not attached, a directory that exists but is empty. Traces feed the `super` entry requirements.
- **Prior grills** — an earlier brief on this topic or a neighbouring one. Read its decisions and open branches; do not re-litigate closed decisions without new evidence, and do surface its unverified assumptions again.

## Budget per level

- **quick:** local only. Minutes, not tens of minutes. Enough to recommend a level and skip D1.
- **deep:** local first (before the setup message), then connected sources and web immediately after the level is confirmed. If a source is large, sample it around the topic keywords; do not read an archive end to end.
- **super:** everything the environment permits, as Stage 0, with the recon report. This is the one place where thoroughness beats speed. Still: sample large sources by relevance, and say what was NOT read.

## Reporting sources

Every fact taken from recon carries its source in the brief: file path, document title, call date, URL with retrieval date. A fact without a source is an assumption and goes in the assumption ledger instead.
