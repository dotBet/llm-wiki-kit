---
type: concept
title: Open Knowledge Format
description: Portable Markdown bundle convention for provenance, trust, lifecycle, and attested computation.
status: stable
updated: 2026-09-09
sources:
  - resource: ../../sources/notes/google-knowledge-catalog-okf-spec.md
    title: Open Knowledge Format v0.2 source note
---

# Open Knowledge Format

## Summary

Open Knowledge Format (OKF) v0.2 is a minimally opinionated convention for portable, agent-readable knowledge bundles: Markdown concept documents, YAML frontmatter, standard links, optional indexes and logs, and explicit metadata for provenance, trust, lifecycle, and attested computation.

## Key Ideas

- A bundle is a directory tree of Markdown documents. Each non-reserved concept document needs parseable frontmatter with a non-empty `type`; producers may add unknown fields and consumers should preserve them.
- Provenance belongs in frontmatter through `sources`, with stable source IDs enabling footnote-level attribution. Objective signals such as author, usage, and modification time inform trust without becoming a universal score.
- `generated` and `verified` answer different questions: who produced the current content and who confirmed it. The actor convention distinguishes tools, people, and automated processes.
- `status` and `stale_after` make lifecycle and freshness explicit. Missing optional trust or lifecycle fields do not make a concept invalid.
- Standard Markdown links form a directed relationship graph. Bundle-root paths are recommended for stability, but consumers must tolerate broken links and unknown types.
- Attested computations separate a readable concept from a sanctioned computation, executor receipt, and deterministic attester. This supports reproducibility without prescribing runtime packaging.

## Evidence

- [OKF v0.2 source note](../../sources/notes/google-knowledge-catalog-okf-spec.md)
- [Pinned specification wrapper](../../sources/raw/google-knowledge-catalog-okf-spec.md)

## Workflow

For an agent-maintained corpus, OKF suggests a useful metadata lifecycle:

1. Write a concept as Markdown with a required `type` and optional descriptive metadata.
2. Record source materials and per-claim attribution in frontmatter and footnotes.
3. Record generation and verification actors separately.
4. Mark lifecycle state and explicit freshness deadlines when relevant.
5. Link concepts into a navigable graph and expose directory contents through indexes.
6. For computed values, link to an `Attested Computation` whose executor receipt can be checked by deterministic code.

## Conflicts

- OKF treats broken links and missing indexes as permissible for consumer tolerance; this wiki still reports them as lint findings because maintainability is stricter than minimum conformance.
- OKF makes `index.md` and `log.md` optional; this repository requires both as operational infrastructure.

## Open Questions

- Should this wiki adopt OKF's `sources`, `generated`, `verified`, `status`, and `stale_after` fields for domain-specific pages?
- Would attested computations help future pages that describe metrics, queries, or other reproducible results?

## Related

- [LLM Wiki Pattern](./llm-wiki-pattern.md)
- [Balanced Citation Policy](../decisions/balanced-citation-policy.md)
- [Lint Workflow](../operations/lint.md)
