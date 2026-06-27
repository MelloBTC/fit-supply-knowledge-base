# Session Handoff - Fit Supply Knowledge Base

Last updated: 2026-06-27

## Purpose

This file is the compact restart surface for the Fit Supply Knowledge Base. It should tell the next session where the project is, what is active, what is gated, and what to do next.

Do not use this file as a running transcript or as compiled wiki truth. Durable knowledge belongs in `wiki/`, source and import status belongs in `raw/`, and stable project framing belongs in `PROJECT_CONTEXT.md`.

## Start Here

Read these files in order when restarting work in this repo:

1. `AGENTS.md`
2. `PROJECT_CONTEXT.md`
3. `docs/session-handoff.md`
4. `schema.md`
5. `wiki/index.md`
6. Relevant domain indexes under `wiki/`
7. `wiki/knowledge-base/agent-answerability-targets.md` when planning content or imports
8. `wiki/knowledge-base/roadmap-import-plan.md` when working from `fast-os-capability-roadmap`
9. `raw/imports/fast-os-capability-roadmap-source-inventory.md` when choosing roadmap artifacts to synthesize

## Current Phase

The project is in target-state skeleton and first roadmap synthesis.

The first durable synthesis pass created compiled wiki pages for the distributor operating model, workflow map, agent capability map, lead-to-closed-won workflow, and close-won-to-delivery workflow.

The first domain model review is complete in `wiki/knowledge-base/domain-model-review.md`.

## Current Boundaries

- Stay in wiki mode.
- Treat this repo as a target-state exemplar for a commercial fitness equipment distributor, using Fit Supply as the concrete example business.
- Use `wiki/` as the compiled knowledge layer and `raw/` for source preservation, inventories, and imports.
- Default new compiled pages to `knowledge_scope: target-state` unless the source clearly requires `reference-pattern`, `design-hypothesis`, or `current-state`.
- Keep `current-state/` quiet until target-state design is more mature.
- Do not bulk-copy roadmap artifacts into wiki truth. Inventory, classify, then synthesize.
- Treat the current `wiki/` folder structure as provisional. Let the stronger `fast-os-capability-roadmap` information architecture influence this repo's domain model instead of forcing roadmap concepts into starter folders.
- Do not replicate active `fast-os-knowledge-base` work on catalog/schema risk, equipment answerability, source manifest patterns, validation gates, or repo-boundary options. Track that lane as an upstream dependency to revisit later.

## Active Source Inventory

The current roadmap inventory is `raw/imports/fast-os-capability-roadmap-source-inventory.md`.

The completed first import slice is:

1. FSCR-002 synthesized into `wiki/company/commercial-fitness-distributor-operating-model.md`.
2. FSCR-003 synthesized into `wiki/knowledge-base/distributor-workflow-map.md`.
3. FSCR-006 synthesized into `wiki/knowledge-base/agent-capability-map.md`.
4. FSCR-007 imported to `raw/imports/fast-os-capability-roadmap/` and synthesized into `wiki/sales/lead-to-closed-won-workflow.md`.
5. FSCR-008 imported to `raw/imports/fast-os-capability-roadmap/` and synthesized into `wiki/projects/close-won-to-delivery-workflow.md`.
6. FSCR-004 remains an upstream dependency owned by `fast-os-knowledge-base`.

## Recommended Next Action

Deepen `order-execution` as the next synthesis lane without changing the top-level domain model yet. Review FSCR-009 and FSCR-010 from `raw/imports/fast-os-capability-roadmap-source-inventory.md`, then synthesize readiness/state material under `wiki/projects/` and governance-heavy gate/review material under `wiki/governance/`.

The domain model review decision is:

- Keep `operating-model` as a canonical lens in `company` for now.
- Keep `agent-workflows` as a `knowledge-base` answerability lens for now.
- Promote `order-execution` as the next active synthesis lane inside `projects` and `governance`.
- Defer `lead-intelligence` and `installed-base` as first-class domains until stronger compiled pages exist.

Do not open commercial equipment catalog/schema or model-specific answerability work locally until `fast-os-knowledge-base` has mature outputs to evaluate.

## Closeout Habit

At the end of a meaningful checkpoint:

- Update this handoff only if the active phase, active source inventory, next action, boundaries, or restart prompt changed.
- Keep this file short and action-oriented.
- Put detailed artifact status in `raw/imports/` or relevant wiki pages, not here.
- For docs-only changes, run `git diff --check` before closing.
- Standing order from Josh: commit and push coherent completed work to `main` after verification passes, unless a Josh decision is needed or the work would switch the repo into a new phase.
- The standing order does not open destructive Git operations, private/raw source imports, pricing/customer/quote material, product or schema implementation, remote tooling, or other gated lanes.
- Include a short restart prompt in the final response or point back to this file.

## Restart Prompt

Continue in `C:\Users\joshm\projects\fit-supply-knowledge-base` from `AGENTS.md`, `PROJECT_CONTEXT.md`, `schema.md`, `wiki/index.md`, and `docs/session-handoff.md`. Stay in wiki mode and use `wiki/knowledge-base/domain-model-review.md` as the domain-structure checkpoint. Next, review FSCR-009 and FSCR-010 from the roadmap inventory and synthesize the order-execution readiness/state lane inside `projects` and `governance` without creating a new top-level domain yet. Keep commercial equipment knowledge-layer work upstream in `fast-os-knowledge-base` until mature enough to evaluate.
