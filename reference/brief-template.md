# The brief — template and state block

The brief is produced at every level and every surface. It has two jobs: to be a self-sufficient input for the next stage of work (a PRD, a memo, an implementation plan) for someone who was not in the session, and to be the resume point for the next grill session on the same topic.

## Where it lives

The rule is: where the next session will find it.

- **Workspace surfaces:** first an existing `grill/` directory from earlier sessions anywhere in the project; else `<docs>/grill/` inside the project's markdown-docs directory (`docs/`, `doc/`, `documentation/`, or wherever `.md` docs clearly live); if neither exists, ask the user once where to create `grill/` and reuse the answer for the whole project. One file per topic: `grill/YYYY-MM-DD-<topic-slug>.md`. A resumed `super` grill keeps its original file and date.
- **Chat surfaces:** a markdown document delivered at the end (and on request mid-session). On resume the user pastes or attaches it; the state block makes it machine-readable enough to continue.

Write the brief incrementally: at the setup message (header + state block), at every wave summary, at every stage end, and at synthesis. A crash at question 17 loses at most the last few answers.

## Template

```markdown
# Grill brief: <topic>

<!-- supergrill-state
status: in_progress | done
level: quick | deep | super
hardness: soft | medium | hard
lens: product | fund | decision | devil | writing | ideas | proof
stage: 0            # super only; 0 = recon report
stage_level: super  # actual level this stage ran at (honest downgrade)
questions_asked: 12
requested_inputs:
  - name: cap table (current)
    reason: stages 3-4 depend on dilution math
    status: received | missing
open_branches:
  - pricing model
  - hiring sequence
next_question: "Which of the two pricing models did the pilot customers actually pay for?"
web_policy: allow | generic-only | skip
updated: 2026-09-16
-->

Date: YYYY-MM-DD | Level | Hardness | Lens | Surface

## Recon (what was known before the first question)
- <fact> — source
- Contradictions found in sources alone: ...
- Traces (mentioned but missing): ...

## Stage plan (super only)
| # | Stage | Branch | Entry requirements | Status |

## Q&A transcript
Q1 (D1): <question>
A1: <answer, condensed> — triage: opinion | private | public ✅/⚠️/❌/❓
...

## Ledger (kept current at every wave)
### ✅ Facts — with source
### 🎯 Decisions — with why
### 🅰 Assumptions — ✓ verified (how) / ✗ unverified (cheapest check)
### ⚠️ Risks — with the user's chosen mitigation
### ❓ Open branches
### 🔍 Contradictions — found / resolved how

## Synthesis (at stage end and at the end)
1. Verdict
2. Decision log
3. Assumption ledger
4. Fact ledger (✅ ⚠️ ❌ ❓ with sources and dates)
5. Contradiction log
6. Risk register
7. Residual ambiguity: goal clarity x/10 · decision-tree coverage x/10 · evidence strength x/10
8. Next step

## Rejected alternatives (with why)
```

## Resume protocol

1. On any grill start, search for briefs whose state block says `status: in_progress` and whose topic matches or neighbours the current one.
2. If one matches: read it, summarise in two sentences where it stopped and what was requested, confirm with the user, and continue from `next_question`. Re-run the consistency pass against anything new the user brought.
3. If the user wants to start over anyway: mark the old brief `status: done` with a note, and start a new file.
