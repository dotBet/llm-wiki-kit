# Sources

This folder holds the ground truth for the wiki.

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

## Rules

- Preserve raw material as much as possible.
- Always create a source note in `notes/` and link the raw file path from it.
- Prefer adding new source notes over rewriting history.
- If a source changes over time, create a dated note.
- Link wiki claims back to source notes or raw files.

## Source Note Lifecycle

- `raw` — captured but not yet extracted into the wiki
- `extracted` — claims pulled into wiki pages
- `reconciled` — wiki pages verified against the source

Suggested format: [source-note.md](../wiki/templates/source-note.md).
