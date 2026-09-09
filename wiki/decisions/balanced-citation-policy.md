---
type: decision
status: current
updated: 2026-07-17
sources: []
---

# Balanced Citation Policy

## Summary

This wiki uses balanced provenance: key claims must be sourced, cross-page inferences are allowed when labeled, and uncertainty is explicit rather than hidden.

## Decision

Adopt three claim tiers for all wiki pages:

1. **Sourced** — non-obvious or disputed facts must link to a source note in `sources/notes/` or a raw file in `sources/raw/`.
2. **Synthesized** — inferences drawn across multiple pages or sources must be tagged with `Synthesis:` and list contributing pages or source notes.
3. **Uncertain** — claims with insufficient evidence go in `Open Questions` or inline as `(uncertain: reason)`.

Well-known facts that are common knowledge in the domain do not require a source link, but should not be stated as precise or disputed claims without evidence.

## Rationale

- **Strict** provenance slows ingestion and encourages transcript-style dumps.
- **Light** provenance lets hallucinations persist as wiki fact.
- **Balanced** keeps the wiki auditable without blocking synthesis — the main value of a compiled wiki over raw RAG.

Synthesis: this decision follows from the risks named in [LLM Wiki Pattern](../concepts/llm-wiki-pattern.md) (hallucinated claims, wiki drift) and the user's bootstrap preference for domain ingestion speed with accountability.

## Evidence

- Source: [Karpathy LLM Wiki source note](../../sources/notes/karpathy-llm-wiki-source-note.md) — gist emphasizes sourced, maintained knowledge over chat ephemera
- Contract: [AGENTS.md](../../AGENTS.md) — claim tiers encoded in Page Conventions

## Related

- [LLM Wiki Pattern](../concepts/llm-wiki-pattern.md)
- [Lint Workflow](../operations/lint.md)
- [Ingest Workflow](../operations/ingest.md)
