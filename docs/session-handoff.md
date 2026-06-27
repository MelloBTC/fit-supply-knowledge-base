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

The hunter-sales / prospecting synthesis lane now exists under `sales` with one design-hypothesis page for existing multifamily policy, reactivation, and validation status. The 2026-06-27 validation-status checkpoint strengthens source-origin routing, service-to-sales replacement signals, grouped-property review, and active-workflow duplicate blocking. A dealer-backed Regency capture now anchors duplicate-outreach blocking once an outbound response becomes active site visit, proposal, bid-collection, approved quote, closed-won, or order-readiness work. A soft-negative split-candidate capture clarifies that negative replies need classification before hard suppression, while remaining policy probes stay provisional.

The wiki-to-agent build bridge now exists under `knowledge-base` with one reference-pattern page for translating mature wiki knowledge into future build-facing agent requirements without opening product schema, agent architecture, live tooling, or implementation specs.

The 2026-06-27 domain pressure recheck is recorded in `wiki/knowledge-base/domain-model-review.md` and still keeps the top-level domain model stable, with source-intelligence, lead-intake, and hunter-sales kept as sales sub-lanes.

The 2026-06-27 information-architecture pressure test is recorded in `wiki/knowledge-base/information-architecture-pressure-test.md`. It confirms Josh's concern that the starter department folders are not the whole target structure. The decision is to keep folders stable for now, use lifecycle, capability, and readiness/state maps as the primary navigation lenses, and migrate folders only when evidence creates real navigation pressure.

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
8. FSCR-012 synthesized into `wiki/sales/hunter-sales-existing-multifamily-pattern.md` as a design-hypothesis page and updated with a 2026-06-27 validation-status checkpoint from real/sanitized example pressure tests, provisional probe results, a soft-negative split-candidate capture, and a dealer-backed Regency active-workflow duplicate-block capture.
9. FSCR-013 synthesized into `wiki/knowledge-base/wiki-to-agent-build-bridge.md` as a reference-pattern page without creating product schema, agent architecture, live tooling, or implementation specs.
10. FSCR-016 synthesized into `wiki/sales/source-aware-lead-intake-routing.md` as a target-state page without importing raw customer, pricing, quote, NetSuite, or source-feed artifacts; updated 2026-06-27 with a Bailey at Berkman formal-feed example capture and a Park at Rialto service-created replacement outcome capture.
11. FSCR-004 remains an upstream dependency owned by `fast-os-knowledge-base`.

## Recommended Next Action

The source-aware lead intake, hunter-sales, and order-execution lanes have been deepened without changing the top-level domain model. Source-aware lead intake now includes one formal-feed dealer example capture and one service-created downstream outcome capture. Hunter-sales now includes one dealer-backed active-workflow duplicate-block capture plus provisional soft-negative split discipline. The current pages are:

- `wiki/sales/source-aware-lead-intake-routing.md`.
- `wiki/projects/order-execution-readiness-agent-requirements.md`.
- `wiki/projects/order-execution-state-model.md`.
- `wiki/governance/order-execution-transition-gate-rules.md`.
- `wiki/sales/hunter-sales-existing-multifamily-pattern.md`.
- `wiki/knowledge-base/wiki-to-agent-build-bridge.md`.
- `wiki/knowledge-base/information-architecture-pressure-test.md`.

Recommended next action: review FSCR-011 if the next checkpoint is evaluation discipline for order-execution gates. If no new sales examples are available, use the information-architecture pressure test to run a navigation cleanup or a non-gated roadmap synthesis pass. Continue the example-first lane only when there is downstream research/outreach/park/quote outcome evidence for the formal-feed source-aware example, another explicit downstream lead-intake outcome, or the next dealer-backed hunter-sales example from the remaining open validation list.

For hunter-sales, the highest-value remaining dealer-backed examples are: a budget-window target or review list, prospecting no-response with touch and buyer-path context, manager-change signal quality, scoped hard stop, a real soft-negative response using the current split-candidate checklist, or sensitive-account review ownership. Do not treat the current validation-status checkpoint, Regency active-workflow capture, or soft-negative split capture as fixture promotion, dealer-approved policy, or build readiness.

The domain pressure decision is:

- Keep `operating-model` as a canonical lens in `company` for now.
- Keep `agent-workflows` as a `knowledge-base` answerability lens for now.
- Keep `order-execution` as an active lane inside `projects` and `governance` for now.
- Keep `source-intelligence`, `lead-intake`, `hunter-sales`, `lead-intelligence`, and `prospecting` as active `sales` sub-lanes for now.
- Keep `wiki-to-agent build bridge` as a `knowledge-base` readiness lens for now.
- Treat domain folders as storage homes and lifecycle/capability/readiness maps as primary navigation lenses for cross-domain workflow content.
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

Continue in `C:\Users\joshm\projects\fit-supply-knowledge-base` from `AGENTS.md`, `PROJECT_CONTEXT.md`, `schema.md`, `wiki/index.md`, and `docs/session-handoff.md`. Stay in wiki mode and use `wiki/knowledge-base/domain-model-review.md`, `wiki/knowledge-base/information-architecture-pressure-test.md`, and `wiki/knowledge-base/wiki-to-agent-build-bridge.md` as the structure and build-readiness checkpoints. The current decision is to keep physical domain folders stable while using lifecycle, capability, and readiness/state maps as primary navigation lenses. The source-aware lead intake lane is synthesized inside `sales` and now includes a Bailey at Berkman formal-feed example capture plus a Park at Rialto service-created replacement outcome capture; the order-execution readiness/state lane is synthesized inside `projects` and `governance`; the hunter-sales existing multifamily lane is synthesized inside `sales` as a design-hypothesis page with a 2026-06-27 validation-status checkpoint, a dealer-backed Regency active-workflow duplicate-block capture, and a soft-negative split-candidate capture. Next, review FSCR-011 if evaluation discipline is the priority; if no new sales examples are available, use the IA pressure test to run navigation cleanup or non-gated roadmap synthesis before any folder migration. Keep commercial equipment knowledge-layer work upstream in `fast-os-knowledge-base` until mature enough to evaluate.
