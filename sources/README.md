# Sources

This folder holds the ground truth for the wiki. Raw material is captured here; the maintained, synthesized knowledge layer lives under [`wiki/`](../wiki/index.md).

## Layout

```text
sources/
  notes/     # source notes (markdown extractions and reconciliations)
  raw/       # immutable originals (PDFs, clips, transcripts, URL wrappers)
  assets/    # images and attachments downloaded from sources (optional)
  README.md
```

## Use For

- Raw documents in `raw/`.
- Source notes in `notes/` (one per source or source revision).
- URLs and citation metadata.
- Meeting notes or pasted transcripts.
- Images in `assets/` when local copies are needed.

For external URLs, capture a small immutable wrapper in `raw/` containing the canonical URL, pinned revision or date when available, and capture date. Do not treat a URL wrapper as a substitute for a source note.

## Rules

- Preserve raw material as much as possible.
- Always create a source note in `notes/` and link the raw file path from it.
- Prefer adding new source notes over rewriting history.
- If a source changes over time, create a dated note.
- Link wiki claims back to source notes or raw files.
- In OKF-compatible wiki pages, represent source provenance with `sources` entries containing at least a `resource` and, when useful, a `title`; add stable `id` values when body footnotes attribute individual claims.

## Source Note Lifecycle

- `raw` — captured but not yet extracted into the wiki
- `extracted` — claims pulled into wiki pages
- `reconciled` — wiki pages verified against the source

Suggested format: [source-note.md](../wiki/templates/source-note.md). The source note should record extracted claims, terms, decisions, conflicts, open questions, and related wiki pages.
