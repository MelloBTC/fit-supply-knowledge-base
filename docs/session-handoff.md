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

The order-execution synthesis lane now exists under `projects` and `governance` with readiness requirements, state model, and transition gate rules.

The source-aware lead intake synthesis lane now exists under `sales` with one target-state page for source event preservation, source-type routing, quote-readiness distance, source-specific first outputs, human review boundaries, research/enrichment, and outcome tracking. The 2026-06-27 example-first captures synthesize the Bailey at Berkman ConstructConnect case as a human-curated formal-feed routing example and the Park at Rialto service-created replacement case as downstream source-to-quote/no-response outcome evidence, without importing raw feed, quote, pricing, or NetSuite artifacts.

The hunter-sales / prospecting synthesis lane now exists under `sales` with one design-hypothesis page for existing multifamily policy, reactivation, and validation status. The 2026-06-27 validation-status checkpoint strengthens source-origin routing, service-to-sales replacement signals, grouped-property review, and active-workflow duplicate blocking while keeping remaining policy probes provisional.

The wiki-to-agent build bridge now exists under `knowledge-base` with one reference-pattern page for translating mature wiki knowledge into future build-facing agent requirements without opening product schema, agent architecture, live tooling, or implementation specs.

The 2026-06-27 domain pressure recheck is recorded in `wiki/knowledge-base/domain-model-review.md` and still keeps the top-level domain model stable, with source-intelligence, lead-intake, and hunter-sales kept as sales sub-lanes.

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
6. FSCR-009 synthesized into `wiki/projects/order-execution-readiness-agent-requirements.md`.
7. FSCR-010 synthesized into `wiki/projects/order-execution-state-model.md` and `wiki/governance/order-execution-transition-gate-rules.md`.
8. FSCR-012 synthesized into `wiki/sales/hunter-sales-existing-multifamily-pattern.md` as a design-hypothesis page and updated with a 2026-06-27 validation-status checkpoint from real/sanitized example pressure tests and provisional probe results.
9. FSCR-013 synthesized into `wiki/knowledge-base/wiki-to-agent-build-bridge.md` as a reference-pattern page without creating product schema, agent architecture, live tooling, or implementation specs.
10. FSCR-016 synthesized into `wiki/sales/source-aware-lead-intake-routing.md` as a target-state page without importing raw customer, pricing, quote, NetSuite, or source-feed artifacts; updated 2026-06-27 with a Bailey at Berkman formal-feed example capture and a Park at Rialto service-created replacement outcome capture.
11. FSCR-004 remains an upstream dependency owned by `fast-os-knowledge-base`.

## Recommended Next Action

The source-aware lead intake and order-execution lanes have been deepened without changing the top-level domain model. Source-aware lead intake now includes one formal-feed dealer example capture. The current pages are:

- `wiki/sales/source-aware-lead-intake-routing.md`.
- `wiki/projects/order-execution-readiness-agent-requirements.md`.
- `wiki/projects/order-execution-state-model.md`.
- `wiki/governance/order-execution-transition-gate-rules.md`.
- `wiki/sales/hunter-sales-existing-multifamily-pattern.md`.
- `wiki/knowledge-base/wiki-to-agent-build-bridge.md`.

Recommended next action: review FSCR-011 only if the next checkpoint is evaluation discipline for order-execution gates. Otherwise, continue the example-first lane: capture downstream research/outreach/park/quote outcome evidence for the formal-feed source-aware example, capture another explicit downstream lead-intake outcome, or capture one hunter-sales example before promoting policy defaults or moving either lane toward build-facing requirements.

For hunter-sales, the highest-value next examples are: a budget-window target or review list, prospecting no-response with touch and buyer-path context, manager-change signal quality, scoped hard stop, soft negative response, or sensitive-account review ownership. Do not treat the current validation-status checkpoint as fixture promotion, dealer-approved policy, or build readiness.

The domain pressure decision is:

- Keep `operating-model` as a canonical lens in `company` for now.
- Keep `agent-workflows` as a `knowledge-base` answerability lens for now.
- Keep `order-execution` as an active lane inside `projects` and `governance` for now.
- Keep `source-intelligence`, `lead-intake`, `hunter-sales`, `lead-intelligence`, and `prospecting` as active `sales` sub-lanes for now.
- Keep `wiki-to-agent build bridge` as a `knowledge-base` readiness lens for now.
- Defer `lead-intelligence`, `installed-base`, and a top-level `order-execution` domain until stronger compiled page density supports the move.

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

Continue in `C:\Users\joshm\projects\fit-supply-knowledge-base` from `AGENTS.md`, `PROJECT_CONTEXT.md`, `schema.md`, `wiki/index.md`, and `docs/session-handoff.md`. Stay in wiki mode and use `wiki/knowledge-base/domain-model-review.md` plus `wiki/knowledge-base/wiki-to-agent-build-bridge.md` as the domain-structure and build-readiness checkpoints. The source-aware lead intake lane is synthesized inside `sales` and now includes a Bailey at Berkman formal-feed example capture plus a Park at Rialto service-created replacement outcome capture; the order-execution readiness/state lane is synthesized inside `projects` and `governance`; the hunter-sales existing multifamily lane is synthesized inside `sales` as a design-hypothesis page with a 2026-06-27 validation-status checkpoint. Next, review FSCR-011 only if evaluation discipline is the priority; otherwise stay example-first by capturing downstream outcome evidence for the formal-feed example, another explicit downstream lead-intake outcome, or one hunter-sales validation example before moving either lane toward build-facing requirements. Keep commercial equipment knowledge-layer work upstream in `fast-os-knowledge-base` until mature enough to evaluate.
