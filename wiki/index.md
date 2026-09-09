---
okf_version: "0.2"
---

# Wiki Index

This is the entry point for the LLM-maintained wiki. Read this catalog first, then drill into relevant pages.

Chronological history: [log.md](./log.md)

## Operations

- [Ingest Workflow](./operations/ingest.md) — turn raw material into durable wiki knowledge
- [Query Workflow](./operations/query.md) — answer from the wiki first, file reusable answers back
- [Lint Workflow](./operations/lint.md) — keep the wiki trustworthy, compact, and navigable

## Concepts

- [LLM Wiki Pattern](./concepts/llm-wiki-pattern.md) — architectural pattern: sources, compiled wiki, agent contract
- [Open Knowledge Format](./concepts/open-knowledge-format.md) — portable Markdown bundle convention for provenance, trust, lifecycle, and attested computation

## Entities

- [Karpathy LLM Wiki Gist](./entities/karpathy-llm-wiki-gist.md) — Andrej Karpathy's April 2026 idea file that defines the pattern

## Decisions

- [Balanced Citation Policy](./decisions/balanced-citation-policy.md) — provenance tiers: sourced, synthesized, uncertain

## Sources Indexed

- [Karpathy LLM Wiki Pattern](../sources/notes/karpathy-llm-wiki-source-note.md) — extracted claims from the primary gist and supporting explainers
- [Open Knowledge Format v0.2](../sources/notes/google-knowledge-catalog-okf-spec.md) — Google Cloud specification for agent-readable knowledge bundles

## Current Scope

This wiki currently captures the general LLM Wiki pattern inspired by Andrej Karpathy's April 2026 gist and the compatible Open Knowledge Format metadata model. The operational spine is in place; ready to ingest domain-specific sources.

## Open Questions

- What domain should this wiki compile first?
