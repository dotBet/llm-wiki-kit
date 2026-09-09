# Source Note: Karpathy LLM Wiki Pattern

Status: extracted

Primary source:

- Andrej Karpathy, `llm-wiki.md`, GitHub Gist: <https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f>
- Raw reference: [../raw/karpathy-llm-wiki-gist.md](../raw/karpathy-llm-wiki-gist.md)

Supporting explainers checked on 2026-05-16:

- Cognition, "`llm-wiki`: the reference implementation of Karpathy's self-building AI memory pattern": <https://www.cognitionus.com/blog/llm-wiki-guide>
- Noze, "LLM Wiki: the pattern of a knowledge base written by the model": <https://www.noze.it/en/insights/llm-wiki/>
- AI Critique, "Andrej Karpathy's latest concept 'LLM Wiki' and the future of enterprise knowledge": <https://www.aicritique.org/us/2026/05/08/andrej-karpathys-latest-concept-llm-wiki-and-the-future-of-enterprise-knowledge/>

## Why This Source Matters

This is the primary source for the meta-pattern this repository implements. All concept, operation, and structural decisions trace back here.

## Extracted Claims

- The pattern uses a persistent Markdown wiki as an intermediate knowledge layer between raw sources and LLM answers.
- The wiki is maintained by the LLM over time, rather than manually authored from scratch by the human.
- The common architecture has three layers: raw sources, compiled wiki, and an operating schema or instruction file.
- The key operations are ingest, query, and lint or maintenance.
- The motivation is to make knowledge compound across sessions instead of being re-derived from raw context on every question.
- `index.md` is content-oriented: a catalog organized by category with one-line summaries.
- `log.md` is chronological: an append-only record of ingests, queries, and lint passes.

## Terms

- **Ingest:** read a source and integrate it across multiple wiki pages.
- **Query:** answer from the wiki first; file reusable answers back into the wiki.
- **Lint:** health-check for contradictions, orphans, stale claims, and missing cross-references.

## Open Questions

- Which source types should this local wiki prioritize first?

## Related Wiki Pages

- [LLM Wiki Pattern](../../wiki/concepts/llm-wiki-pattern.md)
- [Karpathy LLM Wiki Gist](../../wiki/entities/karpathy-llm-wiki-gist.md)
- [Ingest Workflow](../../wiki/operations/ingest.md)
