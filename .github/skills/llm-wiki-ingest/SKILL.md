---
name: llm-wiki-ingest
description: "Ingest sources into this Markdown-first LLM Wiki. Use when capturing material, creating source notes, extracting claims, updating wiki pages, adding citations, or recording an ingest in wiki/log.md."
argument-hint: "Describe the source or material to ingest"
user-invocable: true
disable-model-invocation: false
---

# LLM Wiki Ingest

## Purpose

Turn raw material into durable, sourced, cross-linked wiki knowledge. Treat the wiki as compiled memory, not as a transcript or a single summary dump.

## Before Editing

Read [AGENTS.md](../../../AGENTS.md), [wiki/index.md](../../../wiki/index.md), and the [ingest workflow](../../../wiki/operations/ingest.md). Inspect related wiki pages and determine whether the source is already captured.

## Procedure

1. Capture the source in `sources/raw/`, or add a metadata wrapper for an external URL. Preserve existing raw captures; do not rewrite them.
2. Create or update a source note in `sources/notes/` using the [source note template](../../../wiki/templates/source-note.md). Track its lifecycle as `raw`, `extracted`, or `reconciled`.
3. Extract stable concepts, entities, decisions, workflows, facts, conflicts, and open questions.
4. Update existing concept, entity, decision, or operation pages before creating new pages. One source should usually improve multiple relevant pages.
5. Apply the [balanced citation policy](../../../wiki/decisions/balanced-citation-policy.md): cite non-obvious claims, mark cross-page inferences as `Synthesis:`, and record unresolved claims as uncertain.
6. Add related links and backlinks. Update [wiki/index.md](../../../wiki/index.md) when the page map changes.
7. Append a concise entry to [wiki/log.md](../../../wiki/log.md) describing the ingest and resulting changes.

## Avoid

- Dumping a long source summary without synthesis
- Creating a new page for every source
- Copying claims without provenance
- Treating the wiki as a chat transcript
- Forgetting the index or log update

## Completion Checks

- A raw capture or external-source wrapper exists.
- The source note exists and has the correct lifecycle status.
- Affected wiki pages contain citations, synthesis labels, or uncertainty markers as appropriate.
- New pages are reachable from the index or related pages.
- Raw sources remain unchanged.
- `wiki/log.md` records the operation.

Summarize changed paths, evidence, unresolved questions, and validation performed.
