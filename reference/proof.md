# Lens: proof — verify or refute a claim with evidence

Goal: take a claim ("X is true", "this market is $4B", "our churn is normal for the industry") and establish what can actually be proven, how strongly, and what remains faith. You actively gather evidence, not just ask. Default level: `deep`.

## Protocol

1. **Decompose the claim** — split it into atomic, falsifiable statements. "Our product is the fastest and users love it" = two claims, each needing different evidence. Vague words get operationalised first: "fastest" by what metric, measured how?
2. **Classify each atom** by how it could be verified:
   - **Documentary** — verifiable from provided or available documents, data, archives (check them now).
   - **Public** — verifiable via web research. Apply `fact-check.md`: fetch and read each source, at least two independent sources, prefer primary, date every fact, grade.
   - **Computational** — verifiable by calculation or logic from agreed premises (compute it now, show the maths).
   - **Empirical** — requires a real-world action by the user (a measurement, an A/B test, a phone call, a legal check). Design the exact action: what to do, what result confirms vs refutes, expected cost and time.
   - **Unfalsifiable** — cannot be verified even in principle. Name it honestly; recommend rephrasing or dropping the claim.
3. **Gather** — execute every check you can execute yourself before asking the user anything. Never ask the user to confirm what a source can confirm.
4. **Grade each atom:** ✅ confirmed (evidence, source) / ❌ refuted (evidence, source) / ⚠️ contested (sources disagree — show both) / ⏳ pending user action (with the designed action) / 🚫 unfalsifiable.
5. **Rebuild the claim** — restate the original claim keeping only what survived, with confidence levels. Show the delta between what the user believed and what is proven.

## Rules

- Source quality hierarchy: primary data > official filings and registries > reputable press > vendor marketing > social media. Say which tier each citation is.
- Date every fact; a 2019 market size is not a current market size.
- Distinguish absence of evidence from evidence of absence — explicitly, every time it comes up.
- Your own confidence is also evidence to be graded: if you "remember" a fact but can't source it, mark it ⚠️ and say so.

## Super-level document checklist

- The claim in its original written form and context (who said it, where, when)
- The data behind any private atom (exports, dashboards, contracts)
- Prior verifications or audits of the same claim

Suggested stages for `super`: (1) decomposition and classification; (2) documentary and computational atoms, requires the data; (3) public atoms with full verification; (4) empirical actions designed and the rebuilt claim.

## Output

Brief = evidence report: original claim, atom table (claim / class / evidence / source+date / verdict), the rebuilt defensible claim, pending empirical actions for the user (exact steps), and the bottom line: what changed vs what they walked in believing.
