# Export — offering the brief in other formats

After synthesis, offer the export once, in one line, listing only the formats this environment can actually produce. Never promise a format you cannot deliver here.

## Formats

| Format | Always? | How, when available |
|---|---|---|
| **Markdown** | yes | The brief file itself (workspace) or the document delivered in chat. |
| **HTML page** | if the environment can write a file or publish a page | One self-contained `.html` with inline CSS, no external dependencies: header, recon, the full Q&A transcript, the ledger, the synthesis. Readable on a phone. Light and dark colour schemes via `prefers-color-scheme`. |
| **PDF** | only if a converter is present (e.g. a document-conversion tool or a print-to-PDF capable pipeline) | Convert the markdown or the HTML. If nothing is present, say so and offer the HTML, which any browser prints to PDF. |
| **Word (.docx)** | only if a docx-producing tool or skill is present | Same content as the HTML. If an organisation document skill is named in the local overlay, use it so the document matches house style. |

## Contents of an export

Identical across formats:

1. Title, date, level, hardness, lens, surface.
2. Recon summary with sources.
3. Full Q&A transcript, each answer with its triage and grade.
4. The ledger.
5. The synthesis, including the residual ambiguity score.
6. Rejected alternatives.

## Rules

- The markdown brief is the source of truth. Exports are derived from it, never edited independently.
- No OS-specific scripts and no installation steps inside the protocol. Use what is there; otherwise degrade gracefully to markdown or HTML.
- Do not silently pick a format. Offer, let the user choose, produce, and say where the file is.
