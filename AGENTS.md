# LLM Wiki Operating Contract

You are maintaining a Karpathy-style LLM Wiki.

Your job is to convert raw sources and user corrections into a persistent, cross-linked Markdown knowledge base. Treat the wiki as compiled memory: concise, sourced, structured, and useful for future reasoning.

## Repository Roles

- `sources/raw/`: immutable originals (PDFs, clips, transcripts, URL wrappers). Do not edit content after capture.
- `sources/notes/`: source notes with extracted claims, terms, and open questions.
- `sources/assets/`: optional local images and attachments.
- `wiki/`: maintained knowledge layer. Update this when ingesting, answering, reconciling, or linting.
- `wiki/index.md`: content catalog — update when pages are added or renamed.
- `wiki/log.md`: append-only timeline of ingests, queries, and lint passes.
- `wiki/templates/`: page patterns. Prefer these before inventing a new shape.

## Ingest Rules

When the user asks to ingest material:

1. Capture the source in `sources/raw/` (or add a metadata wrapper for external URLs).
2. Create or update a source note in `sources/notes/` using [source-note.md](wiki/templates/source-note.md).
3. Extract durable facts, terms, procedures, decisions, and open questions.
4. Search the wiki for related pages.
5. Update existing pages before creating new pages. One source should typically touch multiple wiki pages (entity updates, concept synthesis, decision records).
6. Add citations per the balanced claim tiers (see Page Conventions).
7. Add backlinks between related concepts.
8. Record uncertainty, conflicts, and missing evidence explicitly.
9. Update `wiki/index.md` if the map changes.
10. Append an entry to `wiki/log.md`.

## Query Rules

When the user asks a question:

1. Start at `wiki/index.md`.
2. Follow relevant internal links.
3. Use raw sources only to verify, resolve conflict, or fill gaps.
4. Answer from the wiki where possible, citing wiki pages and source notes.
5. If the answer is reusable (comparison, analysis, decision rationale), create or update a wiki page — prefer updating an existing entity or decision page over creating an orphan.
6. If the answer reveals stale, missing, or contradictory wiki knowledge, update the wiki after answering.
7. Append a query entry to `wiki/log.md` when the answer produces wiki changes.

## Lint Rules

When asked to lint or maintain the wiki, check for:

- Unsourced claims (per balanced claim tiers).
- Dead internal links.
- Duplicate pages or overlapping concepts.
- Pages that summarize sources but do not synthesize them.
- Stale decisions or superseded facts.
- Missing backlinks from related pages.
- Open questions that now have answers.
- Orphan pages with no inbound links from the index or Related sections.
- Concepts mentioned repeatedly but lacking their own page.
- `wiki/index.md` out of date versus actual pages.
- `wiki/log.md` missing an entry for the last ingest.

## Page Conventions

### Page Types

- **Concept** (`wiki/concepts/`): cross-cutting ideas and patterns that span multiple entities.
- **Entity** (`wiki/entities/`): nouns with persistent identity — people, tools, systems, papers, products.
- **Decision** (`wiki/decisions/`): dated choices with rationale; mark superseded decisions explicitly.
- **Operation** (`wiki/operations/`): repeatable agent workflows (ingest, query, lint).

Use [entity-page.md](wiki/templates/entity-page.md) for entity pages. Use [wiki-page.md](wiki/templates/wiki-page.md) for concepts, decisions, and operations.

### Formatting

- Use short, descriptive filenames in kebab case.
- Use one H1 per page.
- Keep pages concise and navigable.
- Prefer stable sections: `Summary`, `Key Ideas`, `Workflow`, `Evidence`, `Open Questions`, `Related`.
- Optional YAML frontmatter: `type`, `status`, `updated`, `sources` (Obsidian/Dataview-ready).
- Use relative Markdown links.
- Do not hide disagreements. Use a `Conflicts` section when needed.

### Balanced Claim Tiers

- **Sourced:** non-obvious or disputed facts must link to `sources/notes/...` or `sources/raw/...`.
- **Synthesized:** cross-page inference — tag with `Synthesis:` and list contributing pages or sources.
- **Uncertain:** mark in `Open Questions` or inline as `(uncertain: reason)`.

Well-known domain facts may omit source links, but precise or disputed claims always need evidence.

### Source Note Lifecycle

- `raw` → `extracted` → `reconciled`

Update status in the source note as extraction and verification progress.

## Definition of Done

An update is complete when:

- The wiki has a clear entry path from `wiki/index.md`.
- New claims follow the balanced claim tiers.
- Related pages link to each other.
- `wiki/log.md` has an entry for the operation.
- The change is small enough that a future agent can audit it.
