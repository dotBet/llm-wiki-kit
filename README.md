# LLM Wiki

This repository is a Markdown-first implementation of Andrej Karpathy's LLM Wiki pattern: raw sources stay immutable, the LLM maintains a compact interlinked wiki, and an operating contract tells agents how to ingest, query, and lint the knowledge base.

The goal is compounding knowledge. Each useful source, answer, correction, and synthesis should improve the wiki instead of disappearing into chat history.

## Structure

```text
.
|-- AGENTS.md                  # Operating contract for LLM agents
|-- sources/
|   |-- notes/                 # Source notes (extractions and reconciliations)
|   |-- raw/                   # Immutable originals and URL wrappers
|   `-- assets/                # Optional local images and attachments
|-- wiki/                      # LLM-maintained knowledge layer
|   |-- index.md               # Content catalog (entry point)
|   |-- log.md                 # Append-only operation timeline
|   |-- concepts/              # Cross-cutting ideas and patterns
|   |-- entities/              # People, tools, systems, papers
|   |-- decisions/             # Dated choices with rationale
|   |-- operations/            # Workflows the agent follows
|   `-- templates/             # Page and source note templates
`-- README.md
```

## Core Loop

1. Add raw material to `sources/raw/` and a source note to `sources/notes/`.
2. Ask the LLM to ingest it using [AGENTS.md](./AGENTS.md).
3. The LLM updates pages under `wiki/`, preserving citations back to sources.
4. Ask questions against [wiki/index.md](./wiki/index.md) first, then deeper pages, then raw sources only when needed.
5. File reusable answers back into the wiki.
6. Run the lint checklist before trusting the wiki for important work.

## Obsidian Workflow

This repo includes an `.obsidian/` vault for browsing the wiki:

- Open the repository root as an Obsidian vault.
- Use graph view to see page connections and spot orphans.
- Optional: Obsidian Web Clipper to capture articles into `sources/raw/`.
- Optional: YAML frontmatter on wiki pages supports Dataview queries (tags, dates, source counts).
- The LLM agent edits markdown; Obsidian is the read/browse IDE.

Avoid committing `.obsidian/workspace.json` churn unless you want personal layout settings shared.

## Design Principles

- Sources are the ground truth. Do not rewrite or silently mutate them.
- Wiki pages are compiled knowledge, not transcripts.
- Claims follow balanced provenance: sourced, synthesized, or marked uncertain.
- Links should be explicit and navigable.
- Updates should be incremental: improve existing pages before creating new ones.
- Conflicts are first-class: record disagreements rather than smoothing them away.

## Starting Points

- [Wiki Index](./wiki/index.md)
- [Wiki Log](./wiki/log.md)
- [LLM Wiki Pattern](./wiki/concepts/llm-wiki-pattern.md)
- [Ingest Workflow](./wiki/operations/ingest.md)
- [Query Workflow](./wiki/operations/query.md)
- [Lint Workflow](./wiki/operations/lint.md)

## References

- Andrej Karpathy's original gist: <https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f>
- Noze overview of the pattern: <https://www.noze.it/en/insights/llm-wiki/>
