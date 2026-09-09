---
name: llm-wiki-lint
description: "Lint and maintain this Markdown-first LLM Wiki. Use when checking citations, dead links, duplicate pages, stale claims, missing backlinks, orphan pages, index drift, source-note coverage, or wiki/log.md completeness."
argument-hint: "Describe the wiki area or health concern to inspect"
user-invocable: true
disable-model-invocation: false
---

# LLM Wiki Lint

## Purpose

Keep the wiki trustworthy, compact, and navigable by finding provenance gaps, structural drift, stale knowledge, and missing connections.

## Before Reviewing

Read [AGENTS.md](../../../AGENTS.md), [wiki/index.md](../../../wiki/index.md), and the [lint workflow](../../../wiki/operations/lint.md). Inspect the index, relevant pages, source notes, and log for the requested scope.

## Checklist

Check for:

- Important claims without a balanced provenance tier: sourced, synthesized, or uncertain
- Dead internal links
- Pages with duplicate or overlapping purposes
- Source summaries that lack synthesis
- Stale or superseded decisions and claims
- Missing backlinks between related pages
- Open questions that now have answers
- Source notes not linked from the wiki
- Orphan pages absent from the index or related sections
- Repeated concepts that deserve their own page
- An index that does not match the actual page set
- A missing log entry for the latest ingest or wiki-changing query
- Conflicts that are implied but not explicitly named

## Procedure

1. Define the review scope: full wiki, one page family, or a focused concern.
2. Inspect the index and follow links into the affected pages.
3. Verify local links and compare page claims against source notes where needed.
4. Report findings by severity and path.
5. Fix focused issues when the request authorizes edits; otherwise provide actionable findings without changing content.
6. Preserve disagreements in a `Conflicts` section instead of silently choosing a side.
7. Append a lint entry to [wiki/log.md](../../../wiki/log.md) when edits are made.

## Completion Checks

- Every finding has a concrete path and explanation.
- Changed Markdown pages retain one clear H1 and relative links.
- New or repaired pages are reachable from the index or related pages.
- Source files in `sources/raw/` were not modified.
- The final report states residual risks and any checks that could not be performed.

A clean pass should say so explicitly and still mention meaningful residual risks.
