---
type: entity
status: current
updated: 2026-07-17
sources:
  - ../../sources/notes/karpathy-llm-wiki-source-note.md
---

# Karpathy LLM Wiki Gist

## Summary

Andrej Karpathy's April 2026 GitHub Gist (`llm-wiki.md`) is the primary source for the LLM Wiki pattern: an idea file designed to be pasted into an LLM agent so it can build and maintain a persistent, interlinked Markdown knowledge base.

## Key Facts

- **Author:** Andrej Karpathy
- **Published:** April 2026
- **URL:** <https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f>
- **Format:** Plain-prose idea file, not code — meant for agent collaboration
- **Core operations defined:** ingest, query, lint
- **Special files defined:** `index.md` (content catalog), `log.md` (chronological timeline)

## Relationships

- Defines the pattern documented in [LLM Wiki Pattern](../concepts/llm-wiki-pattern.md)
- Implemented by this repository's [AGENTS.md](../../AGENTS.md) operating contract
- Contrasts with RAG: knowledge is compiled once and kept current, not re-derived per query

## Evidence

- Source: [Karpathy LLM Wiki source note](../../sources/notes/karpathy-llm-wiki-source-note.md)
- Raw reference: [karpathy-llm-wiki-gist.md](../../sources/raw/karpathy-llm-wiki-gist.md)

## Related

- [LLM Wiki Pattern](../concepts/llm-wiki-pattern.md)
- [Balanced Citation Policy](../decisions/balanced-citation-policy.md)
- [Ingest Workflow](../operations/ingest.md)
