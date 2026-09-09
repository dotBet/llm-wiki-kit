---
type: concept
title: LLM Wiki Pattern
description: Architecture for compiling raw sources into a persistent, interlinked Markdown wiki.
status: stable
updated: 2026-09-09
sources: [{ resource: ../../sources/notes/karpathy-llm-wiki-source-note.md, title: Karpathy LLM Wiki source note }, { resource: ../../sources/notes/google-knowledge-catalog-okf-spec.md, title: Open Knowledge Format v0.2 source note }]
---

# LLM Wiki Pattern

## Summary

The LLM Wiki pattern is a knowledge-management architecture where an LLM incrementally compiles raw material into a persistent, interlinked Markdown wiki. The wiki becomes the working memory layer for future questions, decisions, and synthesis.

Source: [Karpathy LLM Wiki source note](../../sources/notes/karpathy-llm-wiki-source-note.md)

## Key Ideas

- Raw sources remain the source of truth.
- The wiki is maintained by the LLM, with human review and corrections.
- The wiki should synthesize knowledge, not merely mirror documents.
- Querying starts from the wiki before falling back to raw sources.
- Maintenance is part of the loop: stale, duplicate, and unsourced pages are cleaned over time.
- `index.md` catalogs pages by category; `log.md` records chronological operations.
- Open Knowledge Format (OKF) shows how Markdown bundles can make provenance, trust, lifecycle, and reproducible computation explicit without requiring a runtime.

## Architecture

```mermaid
flowchart LR
    Sources["sources/: immutable raw material"] --> Ingest["Ingest"]
    Ingest --> Wiki["wiki/: compiled Markdown knowledge"]
    Contract["AGENTS.md: schema and operating rules"] --> Ingest
    Contract --> Query["Query"]
    Contract --> Lint["Lint"]
    Wiki --> Query
    Wiki --> Lint
    Lint --> Wiki
    Query --> Answer["Sourced answer"]
    Query --> WikiUpdate["Wiki update when reusable"]
    WikiUpdate --> Wiki
```

## When It Helps

- Long-lived projects where context needs to survive many sessions.
- Research workflows with recurring questions.
- Team or personal knowledge bases where decisions need provenance.
- Agent workflows that need stable memory without relying only on vector search.

## Risks

- Hallucinated claims can become persistent if they are not sourced.
- Poor page boundaries can create duplicate or conflicting knowledge.
- The wiki can drift from raw sources if linting is skipped.
- Overly broad pages become hard for future agents to update safely.

Synthesis: [Balanced Citation Policy](../decisions/balanced-citation-policy.md) mitigates sourcing risks without blocking cross-page synthesis.

Synthesis: [Open Knowledge Format](./open-knowledge-format.md) provides a compatible metadata vocabulary for making source lineage, verification, freshness, and computation contracts more machine-readable.

## Related

- [Karpathy LLM Wiki Gist](../entities/karpathy-llm-wiki-gist.md)
- [Open Knowledge Format](./open-knowledge-format.md)
- [Balanced Citation Policy](../decisions/balanced-citation-policy.md)
- [Ingest Workflow](../operations/ingest.md)
- [Query Workflow](../operations/query.md)
- [Lint Workflow](../operations/lint.md)
- [Wiki log](../log.md)
