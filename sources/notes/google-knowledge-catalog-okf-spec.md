# Source Note: Open Knowledge Format (OKF) v0.2 Specification

Status: extracted

Primary source:

- Google Cloud Platform, `knowledge-catalog/okf/SPEC.md`, pinned revision `8cf3aba`: <https://github.com/GoogleCloudPlatform/knowledge-catalog/blob/8cf3abaf1ee3d53a12f981cc0ed83d6ffec775e1/okf/SPEC.md>
- Raw reference: [../raw/google-knowledge-catalog-okf-spec.md](../raw/google-knowledge-catalog-okf-spec.md)
- Captured: 2026-09-09

## Why This Source Matters

This specification provides a concrete, interoperable schema for agent-maintained Markdown knowledge bundles. It extends the LLM Wiki pattern with explicit metadata for provenance, trust, lifecycle, freshness, and reproducible computation while remaining readable and portable.

## Extracted Claims

- OKF v0.2 defines a knowledge bundle as a hierarchical directory of Markdown concept documents with YAML frontmatter; the bundle can be distributed as a Git repository, archive, or repository subdirectory.
- A concept document requires only a non-empty `type` frontmatter field. `title`, `description`, `resource`, and `tags` are recommended, while consumers must tolerate unknown types and extension keys.
- `index.md` and `log.md` are reserved filenames with defined directory-listing and update-history roles. Both are optional.
- Provenance is represented in a `sources` frontmatter family. Sources can carry stable IDs for per-claim footnotes plus objective signals such as `author`, `usage_count`, `last_modified`, and `usage_window`.
- Trust and authorship are separate: `generated` records who or what produced the current content, while `verified` records verification events. Consumers derive advisory trust tiers from the actor convention and whether a human verifier is present.
- Lifecycle is represented with `status` values such as `draft`, `stable`, and `deprecated`, plus an optional absolute `stale_after` timestamp.
- Every timestamp-valued field uses an ISO 8601 datetime with an explicit UTC offset.
- Standard Markdown links express relationships between concepts. Absolute bundle-root paths are recommended for stability, while relative paths are also supported. Broken links are tolerated by conformance rules.
- Actor identities use `<producer>/<version>` for tools, `human:<id>` for people, and `process:<id>` for automated processes.
- An `Attested Computation` is a standalone concept with a runtime, typed parameters, an executor that returns a receipt, and a deterministic attester that checks the receipt. The computation can be inline or referenced by path.
- OKF conformance is intentionally permissive: non-reserved Markdown files need parseable frontmatter and a non-empty `type`; optional fields, unknown types, unknown extension keys, broken links, and missing indexes do not make a bundle non-conformant.
- OKF v0.2 supersedes the v0.1 `timestamp` and body `# Citations` conventions with `generated.at` and frontmatter `sources`, while retaining compatibility fallbacks.

## Terms

- **Knowledge Bundle:** A self-contained hierarchical collection of knowledge documents and the unit of distribution.
- **Concept:** One Markdown document representing a unit of knowledge, such as an asset, metric, API, process, or abstract idea.
- **Concept ID:** The bundle-relative file path with its `.md` suffix removed.
- **Credibility signal:** An objective per-source fact used by consumers to infer trust, not a stored score.
- **Trust tier:** An advisory tier derived from `verified`: unverified, machine-confirmed, or human-reviewed.
- **Attested Computation:** A concept carrying a sanctioned computation and the interfaces needed to execute and verify it.
- **Receipt:** Runtime evidence returned by an executor and inspected by an attester; it is not stored in the bundle.

## Decisions

- Decision in the source: keep the core format minimally opinionated and leave taxonomy, storage, serving, query infrastructure, and packaging to producers and consumers.
- Decision in the source: make provenance, trust, lifecycle, and attestation first-class without requiring any of them for basic concept consumption.

## Conflicts

- OKF permits broken cross-links for conformance, while this repository's lint workflow treats dead internal links as maintenance findings. These are compatible policies: broken links may be tolerated by consumers but should still be repaired in a maintained wiki.
- OKF allows optional `index.md` and `log.md`, while this repository requires `wiki/index.md` and `wiki/log.md` as part of its operating contract.

## Open Questions

- Should this wiki adopt a subset of OKF frontmatter, such as `sources`, `generated`, `verified`, `status`, and `stale_after`, for future domain pages?
- Which parts of the Attested Computation contract are useful for this repository's eventual domain-specific knowledge?

## Related Wiki Pages

- [LLM Wiki Pattern](../../wiki/concepts/llm-wiki-pattern.md)
- [Open Knowledge Format](../../wiki/concepts/open-knowledge-format.md)
- [Balanced Citation Policy](../../wiki/decisions/balanced-citation-policy.md)
- [Lint Workflow](../../wiki/operations/lint.md)
