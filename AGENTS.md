# AGENTS.md - Fit Supply Knowledge Base

This file provides instructions for AI agents working with the Fit Supply LLM Wiki.

## Core Rules

- Always operate in wiki mode when interacting with this knowledge base.
- Treat this repo as a target-state exemplar for a commercial fitness equipment distributor, using Fit Supply as the concrete example business.
- Prioritize compiled knowledge in `wiki/` over raw source exploration.
- Use `raw/` to verify, enrich, or repair compiled knowledge.
- Provide clear citations to specific pages, sections, and source paths.
- Respect the governance, knowledge scope, and freshness rules defined in `schema.md`.
- Prefer incremental updates and stronger links over duplicate content.

## Startup Sequence

When beginning work in this repo, read these files first:

1. `AGENTS.md`
2. `PROJECT_CONTEXT.md`
3. `schema.md`
4. `wiki/index.md`
5. The relevant domain `index.md` files under `wiki/`
6. `wiki/knowledge-base/agent-answerability-targets.md` when planning content or imports
7. `wiki/knowledge-base/roadmap-import-plan.md` when working from `fast-os-capability-roadmap`

## Navigation

- Start with `wiki/index.md` and the relevant domain index.
- Use wikilinks and the defined taxonomy to traverse related concepts.
- The `equipment/` domain is especially important and should have strong ontology and relationships.
- Treat `current-state/` as a quiet lane for actual Fit Supply current-state notes, not the main workstream.
- When a domain page does not exist yet, add it only if there is a clear source-backed or answerability-driven reason.
- Expand the domain model when roadmap inventory shows important workflow areas that do not fit the starter skeleton.
- Do not replicate active `fast-os-knowledge-base` work on catalog/schema risk, equipment answerability, source manifest pattern, validation gates, or repo-boundary options. Treat that as upstream work to evaluate later.

## Synthesis and Output

- Synthesize answers from structured wiki content rather than re-deriving from scratch.
- Use `knowledge_scope` to distinguish `target-state`, `reference-pattern`, `design-hypothesis`, and `current-state` pages.
- Flag information that appears stale, incomplete, unsourced, or in conflict.
- Do not turn uncertain source material into confident claims.
- When proposing changes, reference the governance rules in `schema.md`.

## Maintenance Mindset

Act as a careful, long-term wiki maintainer. The goal is to make this target-state knowledge system more accurate, connected, useful, and agent-ready over time.
