# Changelog

## Unreleased

Fixed
- `description` trimmed to 966 characters (the SKILL.md limit is 1,024); duplicate RU/UK trigger forms removed.
- Discovery narrowed: `brainstorm`, `planning session`, and the proactive "what do you think" clause are gone, and the description now says not to auto-invoke on ordinary planning. The user asks to be interrogated.
- Budgets are counted in questions, not minutes: the wall-clock figures are dropped from `SKILL.md`, `reference/levels.md`, and the README, with a note that verification spends the same budget.
- `super` question total corrected to 30–105 across 3–7 stages (the old 50–100 contradicted 3 stages × 10 questions).

Added
- "Read-only contract" section in `SKILL.md`, and a README note on `disallowed-tools` vs `allowed-tools` in Claude Code.

## 1.0.0 — 2026-09-16

First public release. Supersedes the private `grill` skill (v1, seven lenses, single depth).

Added
- Three depth levels: `quick`, `deep`, `super`, with budgets, recommendation rules, honest per-stage downgrade, and session persistence (`reference/levels.md`).
- Reconnaissance before the first question, scaled to the level, with source tiers and a confidentiality rule for web queries (`reference/recon.md`).
- Answer triage (opinion / private fact / public fact), live verification of load-bearing public facts, batched verification per wave, and a consistency pass every wave (`reference/fact-check.md`).
- Brief template with a machine-readable state block and a resume protocol (`reference/brief-template.md`).
- Export rules for markdown / HTML / PDF / DOCX, environment-dependent (`reference/export.md`).
- Super-level document checklists and suggested stage plans in every lens.
- Private overlay `SUPERGRILL.local.md` with an example template.
- README with a paste-into-Claude installer prompt and manual instructions.

Changed
- All organisation-specific references removed from the public protocol; they belong in the overlay.
- Fact ledger and contradiction log added to the final synthesis.
