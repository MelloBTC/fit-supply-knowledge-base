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
6. Relevant domain indexes under `wiki/`, including `wiki/order-execution/index.md` when working on post-close workflow material
7. `wiki/knowledge-base/agent-answerability-targets.md` when planning content or imports
8. `wiki/knowledge-base/roadmap-import-plan.md` when working from `fast-os-capability-roadmap`
9. `raw/imports/fast-os-capability-roadmap-source-inventory.md` when choosing roadmap artifacts to synthesize

## Current Phase

The project is in target-state skeleton and first roadmap synthesis.

The first durable synthesis pass created compiled wiki pages for the distributor operating model, workflow map, agent capability map, lead-to-closed-won workflow, and close-won-to-delivery workflow.

The order-execution lane is now the first bounded promoted wiki domain. `wiki/order-execution/index.md` is the home for post-close readiness, state, transition-gate, delivery/install execution, completion, and relationship-ready handoff pages. The pilot moved the close-won-to-delivery workflow, readiness requirements, state model, and transition gate rules into `wiki/order-execution/`. `wiki/governance/agent-evaluation-fixtures.md` remains in governance because it is a cross-workflow evaluation discipline page, not only an order-execution operating page.

The source-aware lead intake synthesis lane now exists under `sales` with one target-state page for source event preservation, source-type routing, quote-readiness distance, source-specific first outputs, human review boundaries, research/enrichment, and outcome tracking. The 2026-06-27 example-first captures synthesize the Bailey at Berkman ConstructConnect case as a human-curated formal-feed routing example and the Park at Rialto service-created replacement case as downstream source-to-quote/no-response outcome evidence, without importing raw feed, quote, pricing, or NetSuite artifacts.

The freight/install quote-readiness synthesis lane now exists under `sales` with one target-state page for F&I requirement detection, quote context inheritance, missing-context blockers, routine/exception routing, freight mode selection, draft freight/install/extraction estimates, human review/provenance, handoff continuity, actuals learning, and stale freight monitoring. FSCR-017 was classified through the lifecycle, capability, readiness/state, evaluation/build-readiness, storage-domain, and domain-promotion lenses before synthesis. No raw NetSuite tasks, screenshots, quote PDFs, customer names, source amounts, pricing, or private logistics artifacts were imported.

The proposal package readiness synthesis lane now exists under `sales` with one target-state page for project-context readiness, room context and uncertainty, existing equipment/trade-in capture, design asset readiness, ECDESIGN/rendering review, quote/proposal package alignment, vendor branches, interactive proposal parity, proposal delivery, and follow-up state. FSCR-018 was classified through the lifecycle, capability, readiness/state, evaluation/build-readiness, storage-domain, and domain-promotion lenses before synthesis. No raw customer folders, quote PDFs, photos, pricing, contact details, generated proposal assets, or presentation-builder source artifacts were imported.

The hunter-sales / prospecting synthesis lane now exists under `sales` with one design-hypothesis page for existing multifamily policy, reactivation, and validation status. The 2026-06-27 validation-status checkpoint strengthens source-origin routing, service-to-sales replacement signals, grouped-property review, and active-workflow duplicate blocking. A dealer-backed Regency capture now anchors duplicate-outreach blocking once an outbound response becomes active site visit, proposal, bid-collection, approved quote, closed-won, or order-readiness work. A soft-negative split-candidate capture clarifies that negative replies need classification before hard suppression, while remaining policy probes stay provisional.

The wiki-to-agent build bridge now exists under `knowledge-base` with one reference-pattern page for translating mature wiki knowledge into future build-facing agent requirements without opening product schema, agent architecture, live tooling, or implementation specs.

The 2026-06-27 domain pressure recheck is recorded in `wiki/knowledge-base/domain-model-review.md`. It records the order-execution pilot promotion, keeps source-intelligence, lead-intake, hunter-sales, quote-readiness, freight/install, and proposal-readiness as sales sub-lanes, keeps agent-readiness/build-bridge material under `knowledge-base` or `governance`, and defers all broader lane-first folder moves.

The 2026-06-27 information-architecture pressure test is recorded in `wiki/knowledge-base/information-architecture-pressure-test.md`. It confirms Josh's concern that the starter department folders are not the whole target structure. The audit proposed a lane-first `v0.4` target structure, then the bounded pilot promoted only `order-execution`. Do not run the full `v0.4` migration yet.

## Current Boundaries

- Stay in wiki mode.
- Treat this repo as a target-state exemplar for a commercial fitness equipment distributor, using Fit Supply as the concrete example business.
- Use `wiki/` as the compiled knowledge layer and `raw/` for source preservation, inventories, and imports.
- Default new compiled pages to `knowledge_scope: target-state` unless the source clearly requires `reference-pattern`, `design-hypothesis`, or `current-state`.
- Keep `current-state/` quiet until target-state design is more mature.
- Do not bulk-copy roadmap artifacts into wiki truth. Inventory, classify, then synthesize.
- Treat the current `wiki/` folder structure as provisional but do not expand the physical migration beyond the bounded `order-execution` pilot without a new Josh decision.
- Do not replicate active `fast-os-knowledge-base` work on catalog/schema risk, equipment answerability, source manifest patterns, validation gates, or repo-boundary options. Track that lane as an upstream dependency to revisit later.

## Active Source Inventory

The current roadmap inventory is `raw/imports/fast-os-capability-roadmap-source-inventory.md`.

The completed first import slice is:

1. FSCR-002 synthesized into `wiki/company/commercial-fitness-distributor-operating-model.md`.
2. FSCR-003 synthesized into `wiki/knowledge-base/distributor-workflow-map.md`.
3. FSCR-006 synthesized into `wiki/knowledge-base/agent-capability-map.md`.
4. FSCR-007 imported to `raw/imports/fast-os-capability-roadmap/` and synthesized into `wiki/sales/lead-to-closed-won-workflow.md`.
5. FSCR-008 imported to `raw/imports/fast-os-capability-roadmap/` and synthesized into `wiki/order-execution/close-won-to-delivery-workflow.md`.
6. FSCR-009 synthesized into `wiki/order-execution/order-execution-readiness-agent-requirements.md`.
7. FSCR-010 synthesized into `wiki/order-execution/order-execution-state-model.md` and `wiki/order-execution/order-execution-transition-gate-rules.md`.
8. FSCR-011 synthesized into `wiki/governance/agent-evaluation-fixtures.md` as target-state governance; upstream machine-readable fixture files remain in `fast-os-capability-roadmap`.
9. FSCR-012 synthesized into `wiki/sales/hunter-sales-existing-multifamily-pattern.md` as a design-hypothesis page and updated with a 2026-06-27 validation-status checkpoint from real/sanitized example pressure tests, provisional probe results, a soft-negative split-candidate capture, and a dealer-backed Regency active-workflow duplicate-block capture.
10. FSCR-013 synthesized into `wiki/knowledge-base/wiki-to-agent-build-bridge.md` as a reference-pattern page without creating product schema, agent architecture, live tooling, or implementation specs.
11. FSCR-016 synthesized into `wiki/sales/source-aware-lead-intake-routing.md` as a target-state page without importing raw customer, pricing, quote, NetSuite, or source-feed artifacts; updated 2026-06-27 with a Bailey at Berkman formal-feed example capture and a Park at Rialto service-created replacement outcome capture.
12. FSCR-017 synthesized into `wiki/sales/freight-install-quote-readiness.md` as a target-state page without importing raw NetSuite tasks, screenshots, quote PDFs, customer names, source amounts, pricing, or private logistics artifacts.
13. FSCR-018 synthesized into `wiki/sales/proposal-package-readiness.md` as a target-state page without importing raw customer folders, quote PDFs, photos, pricing, contact details, generated proposal assets, or presentation-builder source artifacts.
14. FSCR-004 remains an upstream dependency owned by `fast-os-knowledge-base`.

## Recommended Next Action

The order-execution pilot migration is complete. Use `wiki/order-execution/index.md` as the canonical home for post-close readiness/state/gate navigation. Keep `wiki/governance/agent-evaluation-fixtures.md` in governance, and keep F&I quote-readiness plus proposal package readiness in sales until quote/proposal readiness has enough validated pages to justify its own lane.

Do not run a full `v0.4` folder migration now. The next useful work should be one of these bounded moves:

1. Add a real or sanitized sales-validation example for source-aware lead intake or hunter-sales without promoting provisional policy.
2. Continue another non-gated roadmap workflow family, classifying it against lifecycle, capability, readiness/state, evaluation/build-readiness, storage-domain, and domain-promotion lenses before adding pages.
3. Revisit commercial equipment knowledge-layer outputs only after `fast-os-knowledge-base` has mature material worth evaluating here.

For hunter-sales, the highest-value remaining dealer-backed examples are: a budget-window target or review list, prospecting no-response with touch and buyer-path context, manager-change signal quality, scoped hard stop, a real soft-negative response using the current split-candidate checklist, or sensitive-account review ownership. Do not treat the current validation-status checkpoint, Regency active-workflow capture, or soft-negative split capture as fixture promotion, dealer-approved policy, or build readiness. Do not treat freight/install quote-readiness as a live pricing engine, current rule source, customer-facing quote updater, or build-ready implementation spec. Do not treat proposal package readiness as an autonomous proposal generator, visual generation pipeline, raw project-folder importer, customer-facing proposal sender, or build-ready implementation spec.

The domain pressure decision is:

- Keep `order-execution` as the first promoted pilot domain.
- Keep `operating-model` as a canonical lens in `company` for now.
- Keep `agent-workflows` and `agent-readiness` as knowledge-base/governance answerability lenses for now.
- Keep `source-intelligence`, `lead-intake`, `hunter-sales`, `lead-intelligence`, and `prospecting` as active `sales` sub-lanes for now.
- Keep `quote-readiness`, `pricing-readiness`, `proposal-readiness`, and `freight-install` as active sales readiness sub-lanes for now; do not promote a new top-level domain from the F&I and proposal package pages alone.
- Keep `agent evaluation fixtures` as a `governance` evaluation-readiness lens for now.
- Treat domain folders as storage homes and lifecycle/capability/readiness maps as primary navigation lenses for cross-domain workflow content.
- Defer `lead-intelligence`, `quote-readiness`, `proposal-readiness`, `agent-readiness`, `installed-base`, `accounts-and-sites`, and full `v0.4` migration until stronger compiled page density or validated examples support the move.

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

Continue in `C:\Users\joshm\projects\fit-supply-knowledge-base` from `AGENTS.md`, `PROJECT_CONTEXT.md`, `schema.md`, `wiki/index.md`, `wiki/order-execution/index.md`, and `docs/session-handoff.md`. Stay in wiki mode. Treat `order-execution` as the first promoted pilot domain, not as permission to run the full `v0.4` folder migration. Use the root and knowledge-base indexes before adding pages, classify new roadmap families against the lifecycle/capability/readiness lenses, and keep sales validation example-first. Do not import the upstream fixture bundle, raw F&I quote/task artifacts, raw proposal/project folders, generated proposal assets, private customer/pricing material, or product evaluator/pricing/proposal implementation unless Josh explicitly opens that scope. Keep commercial equipment knowledge-layer work upstream in `fast-os-knowledge-base` until mature enough to evaluate.
