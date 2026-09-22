# Depth levels — quick / deep / super

A level is a contract about budget, evidence, and structure. Hardness (soft / medium / hard) is orthogonal: it governs tone and pressure, not depth.

## Recommendation rule (after quick recon)

Recommend the level in the setup message, first, marked, with one line of reasoning drawn from THIS topic:

- **quick** when: the decision is reversible, the stakes are small, recon already answered most of the structure, or the user has little time. Also the default when the topic is a single narrow question.
- **deep** when: the decision is moderately expensive to undo, the topic has several dependent branches, or recon found material the user's framing does not yet reflect. The default for most planning sessions.
- **super** when: the decision is irreversible, financial, or investor-facing; the topic spans multiple documents or systems; recon found significant sources worth a stage of their own; or the user explicitly asked for the full treatment.

The user confirms or overrides. Never silently run a level the user did not confirm.

## quick — critical zones only

- **Budget:** up to 10 questions.
- **Recon:** local only — the message, attachments, project files, prior briefs, memory. No connected sources, no web.
- **Question policy:** only the zones where a wrong answer is expensive. Skip D1 if recon already defines the terms. Go straight for the load-bearing assumption (D3), the sharpest conflict (D4), and the core (D5).
- **Evidence rule:** answers are triaged, but public facts are only *marked* ✗ unverified in the brief with the cheapest way to verify. No live verification.
- **Waves:** one mid-point ledger at ~5, then synthesis.
- **Brief:** full, but short. The assumption ledger and the "unverified" list are the deliverable.

## deep — the full ladder, adaptive

- **Budget:** 10–30 questions. Say when the budget is at 20 and at 30. Verification is part of the budget, not extra: a load-bearing fact checked before the next question costs a question's worth of it. If a branch needs three checks, spend them and say where the budget now stands.
- **Recon:** local + connected read-only sources + web (subject to the confidentiality rule in `recon.md`). Run the wider recon right after the level is confirmed, before question 2 at the latest.
- **Question policy:** full D1–D5 ladder on every open branch. Every question is shaped by all previous answers and by recon: reference them explicitly ("you said X in your last answer; recon shows Y").
- **Evidence rule:** load-bearing public facts are verified before the next question; other public facts are batched and verified at each wave; private facts are checked against provided documents when possible.
- **Waves:** every ~5 questions, with the consistency pass.
- **Brief:** full, incremental, with fact ledger and contradiction log.

## super — staged, gated, multi-session

`super` is `deep` plus three additions: a recon report, stages with entry requirements, and session persistence.

### Stage 0 — reconnaissance report

Run full recon (all sources the environment permits). Then present a **recon report** and ask the user to confirm it before the first question:

- What I already know about the topic, grouped by source (files / prior briefs / connected sources / web).
- What contradicts what, already, in the sources alone.
- What I could not find and expect exists (drawn from the lens document checklist and from traces found in recon — see below).
- Proposed stage plan: N stages (typically 3–7), each with a name, the branch it covers, an estimated 10–15 questions, and its **entry requirements**.

### Entry requirements per stage

Each stage may require inputs the user must bring before it starts. Requirements are built ONLY from two sources:

1. **The lens document checklist** (bottom of every lens file): the artifacts a topic of this kind normally has.
2. **Traces found in recon**: a document mentioned in a call, a file referenced but missing, an empty directory, a number quoted without its source.

Never invent a requirement from general expectation alone. Every request states three things: *what* (specific enough to find), *why* (which questions depend on it), and *what degrades without it* ("without the cap table, stage 3 runs at `deep` and dilution stays an assumption").

### Honest downgrade

If a stage's entry requirements are not met when it starts, the stage runs at the highest level its inputs support (`deep` or `quick`). Say so plainly in one sentence, record it in the brief's state block (`stage_level`), and continue. Never pretend a stage was `super` when its inputs were missing.

### Session persistence

Each stage is a natural session boundary. After every stage:
- Write the stage ledger and synthesis-so-far to the brief.
- Update the state block: `stage`, `stage_level`, `requested_inputs` with received / missing, `open_branches`, `next_question`.
- Tell the user what to bring for the next stage and that the next session resumes from the brief.

On resume (any later session, any surface), the brief's state block is the source of truth. Re-read it, summarise where things stopped in two sentences, confirm, and continue. Do not re-ask answered questions; do re-check contradictions between stages.

### Budget

Total 30–105 questions across 3–7 stages; 50–80 is typical. Synthesis happens at the end of each stage (partial) and at the end of the last stage (final). The final synthesis includes a **cross-stage consistency pass**: decisions in stage 1 vs answers in stage 5.

## Switching levels mid-session

- **Up:** at the quick or deep budget boundary, offer once: "budget spent — continue at the next level, or synthesise now?"
- **Down:** only per stage in `super` (honest downgrade), or when the user asks.
- Record every switch in the brief.
