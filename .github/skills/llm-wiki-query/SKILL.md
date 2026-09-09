---
name: llm-wiki-query
description: "Answer questions from this Markdown-first LLM Wiki. Use when researching wiki concepts, entities, decisions, or operations, resolving claim conflicts, filing reusable answers back into the wiki, or recording query-driven updates."
argument-hint: "Ask a question about the knowledge captured in the wiki"
user-invocable: true
disable-model-invocation: false
---

# LLM Wiki Query

## Purpose

Answer from the compiled wiki first, then improve the knowledge base when a question reveals reusable insight, a missing claim, or stale information.

## Before Answering

Read [AGENTS.md](../../../AGENTS.md), [wiki/index.md](../../../wiki/index.md), and the [query workflow](../../../wiki/operations/query.md). Follow the index links to relevant concept, entity, decision, and operation pages.

## Procedure

1. Start at [wiki/index.md](../../../wiki/index.md) and follow relevant internal links.
2. Check citations when claims are important, disputed, or precise.
3. Consult `sources/notes/` and `sources/raw/` only when the wiki is missing, stale, or conflicted.
4. Distinguish sourced facts, cross-page synthesis, and uncertainty in the answer.
5. Answer directly and link to the relevant wiki pages and source notes.
6. If the answer is reusable, update an existing wiki page. Prefer an entity, concept, or decision page over an orphan answer page.
7. If the answer reveals a gap, contradiction, stale claim, or open question, repair or record it in the appropriate wiki page.
8. Append a query entry to [wiki/log.md](../../../wiki/log.md) when the query changes the wiki.

## Answer Shape

Include:

- The direct answer
- Relevant wiki pages or source notes
- Uncertainty or conflict
- Any wiki update made because the answer is reusable

Do not create a summary page merely because a question was asked. Prefer improving the existing knowledge graph.

## Completion Checks

- The answer is grounded in the wiki where possible.
- Raw sources were consulted only for verification, conflict resolution, or missing evidence.
- Claims are labeled or cited according to the balanced citation policy.
- Reusable findings are filed into an existing or clearly justified wiki page.
- `wiki/log.md` records any wiki-changing query.

Summarize the answer, consulted evidence, changed paths, and remaining uncertainty.
