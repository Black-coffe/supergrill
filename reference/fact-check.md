# Fact triage and verification inside a grill

A grill built on a false fact at question 3 produces thirty wrong questions. A grill that stops to search after every sentence loses its rhythm. This file balances the two.

## Triage every answer

Silently classify each user answer (and each fact you yourself introduce) as:

- **Opinion** — preference, judgement, intent. Not checkable. Goes to the decision log or assumption ledger.
- **Private fact** — checkable against the user's own documents, code, data, or connected sources. "Our churn is 4%", "the contract has a 90-day notice period".
- **Public fact** — checkable against the world. Market sizes, competitor features, prices, laws, versions, dates, statistics, "everyone in this industry does X".

Then decide whether the fact is **load-bearing**: does the next branch of the decision tree depend on it being true? A load-bearing fact that turns out false changes which questions come next.

## Evidence rule by level

| Level | Private facts | Public facts, load-bearing | Public facts, other |
|---|---|---|---|
| quick | note the document that would confirm | mark ✗ unverified + cheapest check | mark ✗ unverified |
| deep | check against provided documents now if present; else note | **verify before the next question** | batch, verify at the wave summary |
| super | as deep, and request the document as a stage entry requirement if missing | **verify before the next question** | batch, verify at the wave summary |

"Verify before the next question" means: run the check, report the result in one or two lines with the source, then ask the next question — which may now be a different question than you had planned.

## Verification protocol

If the environment has a dedicated fact-checking skill (the local overlay may name it), delegate to it and use its output. Otherwise apply this built-in minimum:

1. **Two independent sources** for anything that matters. Independent means not one quoting the other. Prefer primary sources (official docs, filings, registries, original datasets) over secondary (press, blogs, aggregators).
2. **Actually read them.** A search-result snippet is not a source. Open the page, read the relevant part.
3. **Date every fact.** The retrieval date and, where available, the publication date. A 2019 market size is a 2019 fact.
4. **Grade:**
   - ✅ confirmed — two independent sources agree.
   - ⚠️ contested — sources disagree; show both and the disagreement.
   - ❌ refuted — the evidence says otherwise; say what it says.
   - ❓ unverified — fewer than two sources found, or the check was not run at this level. Never hide this behind confident wording.
5. **Record** every grade with sources in the brief's fact ledger.

If no search or fetch tools are available, do not guess. Mark ❓, list the exact queries or documents that would resolve it, and continue.

## Consistency pass (every wave)

At every wave summary run three comparisons and list the hits under 🔍:

1. **Words vs words** — does any answer in this wave contradict an earlier answer or an earlier decision? Quote both.
2. **Words vs recon** — does any answer contradict what the files, code, archives, or web said? Quote the source.
3. **Words vs documents** — does any answer contradict a document the user provided? Quote the passage.

Each hit becomes the next question, phrased as a choice: "You said X; the source says Y. Which is right, and what changes if it is Y?" Do not resolve contradictions silently in the user's favour or in the source's favour. In `super`, the final synthesis also runs this pass across stages.

## What this is not

This is not a general research task. Verify what the grill depends on, mark the rest, and keep asking. If the user wants a standalone verification of a claim with no plan behind it, the `proof` lens or a dedicated fact-checking skill is the right tool.
