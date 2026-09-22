# Supergrill

**An evidence-first interrogation protocol for Claude.** Before you commit to a plan, an idea, a decision, an investment, or a text, Supergrill reads everything your environment already knows about it, then interviews you one question at a time until the weak points are on the table — with sources, contradictions, and a brief you can hand to the next stage.

It is a *skill*: a markdown protocol Claude follows. No code, no dependencies, no OS-specific tooling. It works in Claude Code, in IDE agents that read skills, and (pasted as instructions) in the Claude web and desktop apps.

```
/supergrill deep hard fund   Series A in Acme
/supergrill quick            should we rename the product
/supergrill super            migrate billing to usage-based pricing
```

---

## What it does differently

| Ordinary Q&A | Supergrill |
|---|---|
| Asks you what it could have read | **Recon first.** Files, prior briefs, memory, connected read-only sources, the web — before question one. |
| One size of conversation | **Three depth levels** with explicit budgets: `quick` (≤10 questions), `deep` (10–30, adaptive), `super` (staged, gated, multi-session). |
| Takes your numbers at face value | **Fact triage on every answer.** Load-bearing public facts are verified before the next question; the rest are graded at each wave. |
| Forgets what you said ten minutes ago | **Contradiction pass every wave.** Words vs words, words vs recon, words vs documents. Every hit becomes the next question. |
| Ends in chat scrollback | **The brief is the session state.** Written incrementally, resumable in a later session, exportable. |
| Praises the idea | **Sycophancy is failure.** "Great idea" is banned until the idea has survived. |

## The three levels

| | `quick` | `deep` | `super` |
|---|---|---|---|
| Questions | up to 10 | 10–30 | 10–15 per stage × 3–7 stages (30–105) |
| Span | one sitting | one sitting | several sessions |
| Recon | local only | + connected sources + web | full, with a recon report you confirm (Stage 0) |
| Evidence | facts marked unverified | load-bearing facts verified live | as deep, plus document gates per stage |
| Structure | critical zones only | full depth ladder, each question shaped by all previous answers | stages with **entry requirements**: bring the cap table before stage 3, or stage 3 honestly runs at `deep` |
| Persistence | brief | brief | brief with a state block; the next session resumes where you stopped |

After a short recon, Supergrill recommends a level with a one-line reason. You confirm or override. In `super`, a stage whose inputs are missing is downgraded openly and recorded — never faked.

## Seven lenses

`product` · `fund` · `decision` · `devil` · `writing` · `ideas` · `proof`

Each lens is a question track for one kind of topic (an investment committee's order for `fund`, an attack sequence for `devil`, a claim-decomposition protocol for `proof`) plus a document checklist that `super` uses to build stage entry requirements. Lenses are auto-detected from the topic or set as an argument.

## Hardness

`soft` · `medium` · `hard` — independent of level. Hardness sets tone and pressure (how dodges are countered, how early the devil's-advocate framing appears). Level sets depth and evidence. A `quick hard` grill is ten brutal questions.

---

## Installation

### Option A — paste this into Claude

Copy the block below into Claude Code (or any Claude surface with file access). Claude detects the operating system and does the rest.

```
Install the Supergrill skill for me.

1. Detect my operating system and shell, and use the matching commands. Do not assume.
2. The Claude Code skills directory is ~/.claude/skills (on Windows: %USERPROFILE%\.claude\skills). Create it if it does not exist.
3. If a directory named "supergrill" or "grill" already exists there, move it OUT of the skills directory to ~/.claude/skills-backup/<name>-<today's date> instead of deleting it. (A backup left inside the skills directory is still loaded as a skill and its triggers would compete with Supergrill's.)
4. Clone https://github.com/Black-coffe/supergrill into ~/.claude/skills/supergrill (git clone; if git is unavailable, download the repository archive and extract it so that SKILL.md sits directly in ~/.claude/skills/supergrill).
5. Copy SUPERGRILL.local.example.md to SUPERGRILL.local.md in that directory, then ask me which connected sources, confidential topics, and organisation skills to put in it. If I say none, leave the file with only the Defaults section.
6. Show me the resulting directory tree and tell me to restart Claude Code so the skill loads.
7. Confirm by listing the trigger words and the three depth levels from SKILL.md.
```

### Option B — by hand

```bash
# macOS / Linux
mkdir -p ~/.claude/skills
git clone https://github.com/Black-coffe/supergrill ~/.claude/skills/supergrill
cp ~/.claude/skills/supergrill/SUPERGRILL.local.example.md ~/.claude/skills/supergrill/SUPERGRILL.local.md
```

```powershell
# Windows (PowerShell)
New-Item -ItemType Directory -Force "$env:USERPROFILE\.claude\skills" | Out-Null
git clone https://github.com/Black-coffe/supergrill "$env:USERPROFILE\.claude\skills\supergrill"
Copy-Item "$env:USERPROFILE\.claude\skills\supergrill\SUPERGRILL.local.example.md" "$env:USERPROFILE\.claude\skills\supergrill\SUPERGRILL.local.md"
```

If you had an earlier `grill` skill, move it out of the skills directory first (for example to `~/.claude/skills-backup/`); anything left inside `~/.claude/skills/` is loaded as a skill and would compete for the same trigger words.

Restart Claude Code. The skill is available as `/supergrill` and triggers on natural language (see the trigger words in `SKILL.md`).

To install for a single project instead, clone into `<project>/.claude/skills/supergrill`.

### Option C — no file access (claude.ai web or desktop)

Open `SKILL.md`, copy its whole content into a Project's custom instructions (or paste it at the start of a conversation), attach the lens file you need from `reference/`, and write: *"Grill me on: …"*. The protocol adapts: questions come as plain text and the brief is delivered as a document.

### Updating

```bash
git -C ~/.claude/skills/supergrill pull
```

Your `SUPERGRILL.local.md` is ignored by git and survives updates.

---

## Usage

```
/supergrill                         auto-detect everything, recommend a level
/supergrill quick                   ten questions, critical zones only
/supergrill deep hard               full ladder, no mercy
/supergrill super fund  <topic>     staged investment-committee grill
/supergrill proof  <claim>          verify or refute a claim
```

Or in natural language, in any language: *"grill me on the launch plan"*, *"прожарь мою идею"*, *"прожар цей план"*, *"stress-test this decision"*.

**A session looks like this:**

1. Supergrill reads what is there (files, prior briefs, connected sources) and proposes: level, hardness, lens, brief location — in one message, with the first question.
2. One question per turn, always with a recommended answer and the reason it is recommended *for this topic*.
3. Every ~5 questions: a ledger (facts with sources · decisions · assumptions verified/unverified · risks · open branches · contradictions found) written to the brief.
4. Synthesis: verdict, decision log, assumption ledger, fact ledger, contradiction log, risk register, a residual-ambiguity score (goal clarity / decision-tree coverage / evidence strength, each 0–10), and the single next step.
5. Offer: export the brief as markdown, or as HTML / PDF / Word when the environment can produce them. Then, once: an adversarial re-read by a fresh reviewer.

**The brief** lives in `grill/YYYY-MM-DD-<topic>.md` inside your project's docs directory (or where you tell it once). It contains a machine-readable state block, so a `super` grill paused after stage 2 resumes at stage 3 in a new session, and a later grill on a neighbouring topic knows what was already decided.

## Read-only by design

A grill reads and asks; it never acts. Nothing is posted, sent, committed, or changed in any connected system during a session — the only things written are the brief and, on request, an export. The rule lives in the protocol, so it holds on every surface; no sandbox enforces it. In Claude Code you can harden it for specific built-in tools with `disallowed-tools` in the frontmatter of your local copy (`allowed-tools` would not help: it pre-approves tools rather than restricting them).

## Private overlay

The public protocol is generic. Your private setup lives in `SUPERGRILL.local.md` (gitignored): names of connected sources, topics that must never reach a web query, organisation skills the grill may hand off to (a fact-checker, a house-style document generator), a glossary, standing constraints. See `SUPERGRILL.local.example.md`.

## Repository layout

```
SKILL.md                        the protocol (this is what Claude loads)
reference/
  levels.md                     quick / deep / super — budgets, recommendation, downgrade, persistence
  recon.md                      what to read before asking; source tiers; confidentiality rule
  fact-check.md                 answer triage, verification protocol, consistency pass
  brief-template.md             brief structure, state block, resume protocol
  export.md                     markdown / HTML / PDF / DOCX rules
  product.md  fund.md  decision.md  devil.md  writing.md  ideas.md  proof.md
                                the seven lenses, each with a super-level document checklist
SUPERGRILL.local.example.md     template for the private overlay
docs/grill/                     the brief from the session in which Supergrill grilled its own design
```

## Design principles

- **Never ask what the environment can tell you.** Recon is not optional; it is scaled to the level.
- **Depth is a contract.** The user always knows how many questions and what evidence standard applies. Budgets are counted in questions, never in minutes.
- **Honest downgrade over fake depth.** A stage without its inputs says so.
- **The brief is the product.** Someone who was not in the session must be able to act on it.
- **No code in the protocol.** Anything that needs OS-specific tooling is out of scope; the environment's own tools are used when present, and the protocol degrades gracefully when they are not.

## Non-goals (v1)

Marketplace packaging, hooks, new lenses beyond the seven, bundled converters for PDF/DOCX, and tested support for agents other than Claude. The protocol is plain markdown and may well work elsewhere; that is not claimed.

## Provenance

Supergrill grew out of a private `grill` skill used across a dozen projects. Its own design was decided in a `hard product` grill; the brief is in `docs/grill/`.

## License

MIT — see `LICENSE`.
