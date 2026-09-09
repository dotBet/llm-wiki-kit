---
type: Operation
title: Ingest Workflow
description: Turn raw material into durable wiki knowledge.
status: stable
---

# Ingest Workflow

## Purpose

Turn raw material into durable wiki knowledge.

## Steps

1. Capture the source in `sources/raw/` (or add a metadata wrapper for an external URL).
2. Create a source note in `sources/notes/` using [source-note.md](../templates/source-note.md).
3. Optionally discuss key takeaways with the user before writing wiki pages.
4. Extract stable concepts, entities, decisions, workflows, facts, conflicts, and open questions.
5. Search the wiki for related pages.
6. Update existing pages before creating new pages. One source should typically touch **multiple** wiki pages — entity updates, concept synthesis, and decision records — not a single summary dump.
7. Add citations per the [balanced claim tiers](../../AGENTS.md) in `AGENTS.md`.
8. Add related links and backlinks.
9. Update [index.md](../index.md) when the map changes.
10. Append an entry to [log.md](../log.md).

## Output

An ingest should leave behind:

- A raw capture or reference in `sources/raw/`.
- A source note in `sources/notes/`.
- One or more improved wiki pages across concepts, entities, and/or decisions.
- Clear citations.
- Any unresolved questions or conflicts.
- A log entry.

## Anti-Patterns

- Dumping long summaries without synthesis.
- Creating a new page for every source.
- Copying claims without provenance.
- Treating the wiki as a chat transcript.
- Forgetting to update the index or log.

## Related

- [Balanced Citation Policy](../decisions/balanced-citation-policy.md)
- [Source note template](../templates/source-note.md)
- [Entity page template](../templates/entity-page.md)
