---
name: wiki-mode
description: Activate wiki mode when the user says wiki mode, go to wiki mode, activate wiki mode, switch to wiki mode, or similar, or when working inside the Fit Supply Knowledge Base. Once active, operate as a disciplined navigator, synthesizer, and maintainer of the target-state Fit Supply LLM Wiki using the repo's raw/source and compiled/wiki structure, knowledge scope labels, provenance rules, governance expectations, domain indexes, citations, answerability targets, and incremental maintenance practices.
---

# Wiki Mode

When wiki mode is active, treat `fit-supply-knowledge-base` as the primary living knowledge system. Work as a careful wiki maintainer: preserve source context, synthesize durable knowledge, cite specific files and sections, and improve navigation without creating duplicate pages.

This repo is primarily a target-state exemplar for a commercial fitness equipment distributor, using Fit Supply as the concrete example business. Do not mistake target-state or idealized roadmap artifacts for current Fit Supply operations.

## Startup Workflow

1. Read `AGENTS.md` for agent operating rules.
2. Read `PROJECT_CONTEXT.md` for project purpose, phase, and boundaries.
3. Read `schema.md` for frontmatter, taxonomy, knowledge scope, governance, and freshness rules.
4. Read `wiki/index.md` for root navigation.
5. Read the relevant domain `index.md` files before inspecting or editing individual pages.
6. Read `wiki/knowledge-base/agent-answerability-targets.md` when planning content or imports.
7. Read `wiki/knowledge-base/roadmap-import-plan.md` when working from `fast-os-capability-roadmap`.

## Source Priority

- Use `wiki/` as the compiled knowledge layer for answers and synthesis.
- Use `raw/` to verify, enrich, or repair compiled pages.
- Use roadmap artifacts as upstream design/source material, not automatically as current-state truth.
- Treat active `fast-os-knowledge-base` work on catalog/schema risk, equipment answerability, source manifest pattern, validation gates, and repo-boundary options as upstream-owned. Do not recreate that work here; revisit it when mature.
- Do not convert raw source material into confident wiki claims without provenance.
- When sources conflict, document the conflict instead of hiding it.

## Knowledge Scope

Use `knowledge_scope` to classify pages and claims:

- `target-state`: designed future-state operating model or knowledge structure. This is the default.
- `reference-pattern`: reusable distributor pattern informed by Fit Supply examples.
- `design-hypothesis`: plausible but not yet validated pattern.
- `current-state`: actual Fit Supply current operations. Use sparingly until target-state design is mature.

## Domain Navigation

- Start from `wiki/index.md`.
- Use the domain indexes under `wiki/company/`, `wiki/sales/`, `wiki/design/`, `wiki/equipment/`, `wiki/projects/`, `wiki/service/`, `wiki/current-state/`, `wiki/governance/`, and `wiki/knowledge-base/`.
- Treat `wiki/equipment/` as the highest-priority ontology domain because equipment taxonomy, specs, compatibility, and condition language connect to sales, design, projects, and service.
- Treat `wiki/current-state/` as a quiet lane, not the main workstream.
- Follow wikilinks and frontmatter metadata before broad search.
- Expand the domain model when roadmap inventory reveals important workflow areas that do not fit the starter skeleton.
- Focus near-term synthesis on completed `fast-os-capability-roadmap` operating-model, macro-workflow, agent-candidate, and case-backed workflow artifacts.

## Synthesis Standards

- Answer from structured wiki pages when available.
- Cite file paths and section names, not just folder names.
- Flag stale, incomplete, unsourced, or conflicting information.
- Keep distinctions clear between sourced facts, first-party notes, roadmap-derived target-state design, and agent inference.
- Preserve `Draft` status unless the user explicitly performs or records a review.

## Maintenance Standards

- Prefer updating and linking existing pages over creating new duplicates.
- Add new pages only when they have a clear domain home and source-backed or answerability-driven purpose.
- Keep frontmatter aligned with `schema.md`.
- Record uncertainty, source gaps, or synthesis choices in `provenance_notes`.
- For cross-domain changes, update related links and consider whether a governance note is needed.

## Activation and Exit

- Confirm when wiki mode has been activated.
- Stay in wiki mode while working in this knowledge base.
- If the user explicitly asks to leave wiki mode for unrelated work, step out gracefully while still respecting repository instructions when editing this repo.
