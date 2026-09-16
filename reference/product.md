# Lens: product — features, apps, specs, engineering plans

Goal: leave the session with a build-ready understanding — scope, approach, and edge cases resolved before any code or task breakdown.

## Question tracks (climb D1→D5 within each)

1. **Problem & user** — who exactly hits this problem, how often, what do they do today? What breaks if we do nothing?
2. **Success criteria** — how will we KNOW it worked? A number, a behaviour, a date. "Users will like it" is not a criterion.
3. **Scope & anti-scope** — what is explicitly OUT? The anti-scope list is as important as the feature list.
4. **Approach fork** — before details: propose 2–3 genuinely different approaches with trade-offs, recommend one, let the user choose. Never grill details of an approach the user hasn't picked.
5. **Data & states** — what entities exist, what states can each be in, what transitions are legal? Invent edge-case scenarios and walk them: "user deletes the account mid-payment — what happens?"
6. **Failure modes** — what fails, what does the user see, what do we log, who gets paged?
7. **Dependencies & sequencing** — what must exist first? What can ship independently (vertical slices)?

## Workspace behaviours (when a codebase is present)

- Explore before asking: stack, existing patterns, similar features already implemented.
- Cross-examine claims against code: "you said cancellations are partial, but the code cancels whole orders — which is right?"
- **Terminology discipline:** when the user's term conflicts with the project glossary (a `CONTEXT.md`, the local overlay glossary, or equivalent) — call it out; when a term is fuzzy, propose a canonical one. Offer to record resolved terms in the glossary.
- **Decision records:** offer an ADR only when ALL three hold: hard to reverse + surprising without context + a real trade-off existed. Otherwise skip.

## Super-level document checklist

Typical inputs for a product topic. Use to build stage entry requirements; request only what recon shows a trace of or what a stage's questions genuinely depend on.

- Existing spec, PRD, or issue thread for the feature
- Usage or analytics data for the affected flow (how many users, how often)
- Support tickets or user complaints on the problem
- The current data model or schema for the entities involved
- Architecture notes or diagrams for the affected components
- Test suite or QA notes for the touched area
- Roadmap or release calendar (sequencing constraints)
- Competitor implementations of the same feature (screenshots, docs)

Suggested stages for `super`: (1) problem, users, success criteria; (2) scope and approach fork; (3) data, states, edge cases; (4) failure modes and operations; (5) dependencies, sequencing, slices.

## Output & handoff

Brief includes: chosen approach + rejected alternatives (with why), scope/anti-scope, entity/state notes, edge-case decisions, failure-mode table.
Handoff offer: turn the brief into a PRD / implementation plan / task breakdown.
