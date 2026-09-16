# SUPERGRILL.local.md — private overlay (example)

Copy this file to `SUPERGRILL.local.md` next to `SKILL.md` (for all projects) or into a project root (for that project only). The public protocol reads it before recon and never hardcodes anything in it. The real file is gitignored.

Everything here is optional. Delete what you do not use.

## Defaults

- default_level: deep
- default_hardness: medium
- default_lens: (leave empty to auto-detect)
- brief_directory: docs/grill

## Connected sources (read-only)

List the knowledge sources the agent may read during recon and how to recognise them. One line each: name, what it holds, when it is relevant.

- call-archive — meeting and call transcripts via the `recall` tools — relevant for any topic that was discussed with people
- site-analytics — web analytics via the `statable` tools — relevant for product and marketing topics
- public-filings — SEC filings via the `edgartools` tools — relevant for the `fund` lens on public comparables

## Confidential by default

Topics or identifiers that must never appear in a web query. Recon asks or strips them.

- names of portfolio companies and pipeline deals
- names of counterparties in negotiations
- internal project codenames: ...

## Organisation skills the grill may hand off to

- fact-checking: `fact-check` skill — delegate every public-fact verification here
- fund documents: `readiness-fund-docs` skill — use for the investment memo / DD report handoff and for Word exports in house style

## Glossary

Canonical terms the grill should enforce (and call out when the user drifts).

- "pilot" = a paid engagement with a signed scope; unpaid trials are "trials"
- "ARR" = contracted annual recurring revenue, not run-rate

## Standing constraints

Facts the grill should treat as given without asking.

- The fund invests EUR 250k–2M tickets, pre-seed to seed, Europe.
- All product work targets the existing Python stack; no new languages without an ADR.
