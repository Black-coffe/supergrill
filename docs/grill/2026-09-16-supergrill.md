# Grill brief: Supergrill (grill 2.0)

<!-- supergrill-state
status: done
level: deep
hardness: hard
lens: product
questions_asked: 13
open_branches: []
updated: 2026-09-16
-->

Date: 2026-09-16 | Level: deep (run under grill v1, retrofitted) | Hardness: hard | Lens: product | Surface: Claude Code

This is the brief from the session in which the author was grilled about turning the private `grill` skill into the public Supergrill. Answers are condensed.

## Recon (before the first question)

- grill v1: `SKILL.md` (121 lines) + seven lens files; global skill; backups from 2026-09-04 show one change (fact-check delegation). — source: skill directory
- Ten projects on disk have a `docs/grill/` or `grill/` directory: the skill is in active use. — source: filesystem
- GitHub CLI authenticated; public repos already exist for other tools by the same author (pattern: publish method tools). — source: `gh auth status`, projects directory
- Everything the author described (recon, levels, stages, document requests, exports) is prompt-level behaviour; no code required. — source: analysis of the request vs the v1 protocol

Contradiction found in the request itself: the "medium" level was described as the one where previous answers shape later questions, but v1 already does this at every level. Resolved in Q3: levels differ by budget and evidence requirements, not adaptivity.

## Q&A transcript

Q1 (D1) What is Supergrill as a product? — A: A Claude Code skill package (markdown protocol, no code).
Q2 (D1) Relationship to the existing grill skill? — A: Supersedes it; installs over it with a backup; repo named supergrill.
Q3 (D2/D4) Who chooses the depth level, and can it change mid-session? — A: Skill recommends after recon, user confirms, level may be honestly downgraded per stage.
Q4 (D2) What may recon do without permission? — A: Local and read-only connected sources automatically; web automatically except for confidential topics (ask once); never write externally.
(User addition mid-session) A brief must always be saved where the next session finds it; offer export as markdown / HTML / PDF / Word.
Q5 (D3) Where does the super-level document request list come from? — A: Lens checklist + traces found in recon; every request with a reason; no free-form guessing.
Q6 (D2) Recon budget before the first question? — A: Scales with level: quick local only; deep + sources + web; super full with a Stage 0 report.
Q7 (D5) Why a public repository at all? — A: Portfolio and reputation: show the method. Success = a stranger can run it from the README.
Q8 (D4) How to separate the public method from private integrations (fund, call archive, fact-check, document skills)? — A: Generic core + local overlay file, gitignored, with a template.
Q9 (D2) When does fact-checking and contradiction detection run? — A: Triage every answer; load-bearing public facts verified before the next question; rest per wave; consistency pass every wave.
Q10 (D2) How does a multi-stage super grill survive session breaks? — A: The brief is the session state, with a state block; new session resumes from it.
Q11 (D1) Level names? — A: quick / deep / super.
Q12 (D1) Anti-scope for v1? — A: No bundled PDF/DOCX code, no marketplace plugin or hooks, no new lenses, no tested support for other agents, nothing that needs OS-specific programming.
Q13 (D1) License? — A: MIT.
(User addition mid-session) README must contain technical install instructions and a copy-paste prompt that lets Claude install the skill itself.

## Ledger

### ✅ Facts
- v1 is used in ten projects (filesystem).
- v1 already adapts questions to previous answers (SKILL.md, depth ladder and decision tree).
- Author publishes method tools publicly as a pattern (projects directory).

### 🎯 Decisions
1. Skill package, no code.
2. Supersedes grill; backup on install.
3. Recon → recommend level → confirm → honest per-stage downgrade.
4. Recon permissions: local and read-only automatic; web except confidential; never write.
5. Brief always; export offered in environment-available formats.
6. Document requests from lens checklist + recon traces, each with a reason.
7. Recon scales with level; super has Stage 0 recon report.
8. Purpose: show the method; README clarity is the success criterion.
9. Generic core + gitignored local overlay.
10. Fact triage per answer; live verification of load-bearing public facts; consistency pass per wave.
11. Brief is session state with a state block; resume protocol.
12. Names: quick / deep / super.
13. Anti-scope: no converters, no plugin/hooks, no new lenses, no other-agent support claims, no OS-specific code.
14. MIT.
15. README: install instructions + self-install prompt for Claude.

### 🅰 Assumptions
- ✓ Levels differ by budget and evidence, not adaptivity — confirmed by decisions 3, 7, 10.
- ✗ A stranger can run Supergrill from the README alone — verify by giving the README to someone who has never seen grill and watching them install and run a `quick` grill.
- ✗ The overlay mechanism is enough to keep the author's private setup working without a fork — verify in the first week of real use.

### ⚠️ Risks
- Super may over-request documents → mitigated by decision 6 (traces + checklist + reason).
- Recon delays the first question → mitigated by decision 7 (scaled recon).
- Two skills with overlapping triggers on one machine → mitigated by decision 2 (replace, do not coexist).
- Public protocol drifts from the author's local copy → mitigated by decision 9 (overlay, single source).

### 🔍 Contradictions
- "Medium level = adaptive" vs v1 already adaptive → resolved (Q3): levels are about budget and evidence.
- "User picks level up front" vs "stage degrades if documents missing" → resolved (Q3): recommend, confirm, honest downgrade.

## Synthesis

1. **Verdict.** Supergrill is grill 2.0: the same markdown protocol, no code, with three depth levels, recon that scales with level, fact triage on every answer, a contradiction pass every wave, a brief that is the session state and survives session breaks, and a generic core plus a private overlay. Published under MIT as a portfolio of the method. Anything requiring OS-specific code is out.
2. **Decision log.** See above, 15 decisions.
3. **Assumption ledger.** One confirmed, two open (README test, overlay sufficiency).
4. **Fact ledger.** No public facts were load-bearing in this session; all facts are local (filesystem, skill files).
5. **Contradiction log.** Two, both resolved.
6. **Risk register.** Four, each with a mitigation decision.
7. **Residual ambiguity.** Goal clarity 9/10 · decision-tree coverage 8/10 · evidence strength 6/10 (the README-clarity assumption can only be tested by a stranger).
8. **Next step.** Build the repository, install it over the local grill, publish, then hand the README to one person who has never used grill.

## Rejected alternatives
- Standalone CLI / MCP server: large build, loses chat surfaces. Rejected Q1.
- Two skills side by side: overlapping triggers. Rejected Q2.
- Full recon at every level: quick stops being quick. Rejected Q6.
- Two branches (public / private): merge burden, drift. Rejected Q8.
- Verify every fact immediately: breaks rhythm. Rejected Q9.
- Verify only at the end: builds on false facts. Rejected Q9.
