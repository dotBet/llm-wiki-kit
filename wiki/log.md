# Wiki Log

Append-only timeline of ingests, queries, lint passes, and structural changes.

Format: `## [YYYY-MM-DD] type | Title`

---

## [2026-09-09] maintenance | Actualize repository READMEs

- Updated the root README with OKF v0.2 compatibility, the current directory map, and the three split wiki skills
- Updated source-layer READMEs with source-note lifecycle, immutable URL-wrapper, and structured provenance guidance

## [2026-09-09] maintenance | Apply OKF v0.2 metadata model

- Added `okf_version: "0.2"` to the bundle index and OKF-compatible frontmatter to maintained concept, entity, decision, and operation pages
- Normalized lifecycle values and structured `sources` metadata
- Updated [AGENTS.md](../AGENTS.md), page templates, and the [Lint Workflow](./operations/lint.md) to preserve the OKF-compatible conventions

## [2026-09-09] ingest | Open Knowledge Format v0.2

- Captured the pinned Google Cloud Knowledge Catalog specification as an immutable URL wrapper and extracted source note
- Added [Open Knowledge Format](./concepts/open-knowledge-format.md) covering bundle structure, provenance, trust, lifecycle, links, conformance, and attested computation
- Linked the concept from [LLM Wiki Pattern](./concepts/llm-wiki-pattern.md), updated [Balanced Citation Policy](./decisions/balanced-citation-policy.md), and refreshed the [wiki index](./index.md)

## [2026-07-17] bootstrap | Wiki pattern structure

- Created `wiki/log.md`, expanded `wiki/index.md` into categorized catalog
- Added `wiki/entities/`, `wiki/decisions/`, `sources/notes/`, `sources/raw/`, `sources/assets/`
- Extended `AGENTS.md` with page types, balanced claim tiers, and log requirements
- Updated ingest, query, and lint operation pages
- Added optional frontmatter to wiki-page template; created entity-page template
- Moved Karpathy source note to `sources/notes/`; added raw source reference

## [2026-07-17] ingest | Karpathy LLM Wiki Pattern (reconciliation)

- Reconciled seed source note to `extracted` status in new layout
- Created entity page: [Karpathy LLM Wiki Gist](./entities/karpathy-llm-wiki-gist.md)
- Created decision page: [Balanced Citation Policy](./decisions/balanced-citation-policy.md)
- Updated [LLM Wiki Pattern](./concepts/llm-wiki-pattern.md) with cross-links and new source paths

## [2026-07-17] query | How does balanced provenance work?

- Answered from wiki pages and filed reusable rationale into [Balanced Citation Policy](./decisions/balanced-citation-policy.md)
- No new open questions surfaced
