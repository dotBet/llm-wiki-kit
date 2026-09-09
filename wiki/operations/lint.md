# Lint Workflow

## Purpose

Keep the wiki trustworthy, compact, and navigable.

## Checklist

- Every important claim follows the [balanced claim tiers](../../AGENTS.md) (sourced, synthesized, or marked uncertain).
- Internal links resolve.
- Pages have one clear purpose.
- Related pages link to each other.
- Duplicate concepts are merged or cross-linked.
- Conflicts are named explicitly.
- Open questions are still open.
- Source notes in `sources/notes/` are linked from the wiki.
- Orphan pages have no inbound links from the index or Related sections.
- Concepts mentioned repeatedly across pages but lacking their own page.
- Stale claims where newer source notes supersede wiki text.
- [index.md](../index.md) is current versus actual pages.
- [log.md](../log.md) has an entry for the last ingest.

## Suggested Review Cadence

- After every substantial ingest.
- Before using the wiki for important external work.
- When repeated queries expose missing or contradictory knowledge.

## Output

A lint pass should produce either:

- A clean bill of health with residual risks, or
- A small set of edits that improves source coverage, structure, links, or conflicts.

Append a lint entry to [log.md](../log.md) when edits are made.

## Related

- [Balanced Citation Policy](../decisions/balanced-citation-policy.md)
- [Ingest Workflow](./ingest.md)
- [Query Workflow](./query.md)
