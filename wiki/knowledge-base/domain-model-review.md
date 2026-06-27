---
title: Domain Model Review
type: Governance
domain: knowledge-base
knowledge_scope: target-state
status: Draft
last_reviewed:
reviewed_by:
sources:
  - PROJECT_CONTEXT.md
  - docs/session-handoff.md
  - schema.md
  - raw/imports/fast-os-capability-roadmap-source-inventory.md
  - wiki/company/commercial-fitness-distributor-operating-model.md
  - wiki/knowledge-base/distributor-workflow-map.md
  - wiki/knowledge-base/agent-capability-map.md
  - wiki/knowledge-base/wiki-to-agent-build-bridge.md
  - wiki/knowledge-base/information-architecture-pressure-test.md
  - wiki/sales/source-aware-lead-intake-routing.md
  - wiki/sales/lead-to-closed-won-workflow.md
  - wiki/sales/hunter-sales-existing-multifamily-pattern.md
  - wiki/sales/freight-install-quote-readiness.md
  - wiki/projects/close-won-to-delivery-workflow.md
  - wiki/projects/order-execution-readiness-agent-requirements.md
  - wiki/projects/order-execution-state-model.md
  - wiki/governance/order-execution-transition-gate-rules.md
  - wiki/governance/agent-evaluation-fixtures.md
related:
  - [[roadmap-import-plan|Roadmap Import Plan]]
  - [[agent-answerability-targets|Agent Answerability Targets]]
  - [[information-architecture-pressure-test|Information Architecture Pressure Test]]
  - [[wiki-to-agent-build-bridge|Wiki To Agent Build Bridge]]
  - [[distributor-workflow-map|Distributor Workflow Map]]
  - [[agent-capability-map|Agent Capability Map]]
  - [[../company/commercial-fitness-distributor-operating-model|Commercial Fitness Distributor Operating Model]]
  - [[../sales/source-aware-lead-intake-routing|Source-Aware Lead Intake And Routing]]
  - [[../sales/lead-to-closed-won-workflow|Lead To Closed Won Workflow]]
  - [[../sales/hunter-sales-existing-multifamily-pattern|Hunter Sales Existing Multifamily Pattern]]
  - [[../sales/freight-install-quote-readiness|Freight And Install Quote Readiness]]
  - [[../projects/close-won-to-delivery-workflow|Close Won To Delivery Workflow]]
  - [[../projects/order-execution-readiness-agent-requirements|Order Execution Readiness Agent Requirements]]
  - [[../projects/order-execution-state-model|Order Execution State Model]]
  - [[../governance/order-execution-transition-gate-rules|Order Execution Transition Gate Rules]]
  - [[../governance/agent-evaluation-fixtures|Agent Evaluation Fixtures]]
agent_answerability:
  - Should this wiki create a new top-level domain or keep a concept inside the current domain model?
  - Which roadmap-derived concept should become the next synthesis lane?
  - What evidence would justify promoting a workflow lens into a first-class domain?
tags:
  - domain-model
  - roadmap-derived
  - wiki-maintenance
provenance_notes: Domain review checkpoint based on the first roadmap synthesis pass and source inventory. Updated 2026-06-27 with pressure rechecks after order-execution, source-aware lead intake, hunter-sales synthesis, FSCR-011 evaluation discipline synthesis, FSCR-013 bridge closure, and FSCR-017 freight/install quote-readiness synthesis. This page records wiki structure decisions, not current Fit Supply operating facts.
---

# Domain Model Review

This page records the first domain model review after the initial roadmap synthesis pass, plus a pressure recheck after the order-execution and hunter-sales synthesis lanes were added.

The review question is whether the starter wiki domains should expand before more roadmap artifacts are synthesized. The short answer is: keep the top-level domain model stable for now, treat `order-execution` as an active workflow lens, and treat `source-intelligence`, `lead-intake`, and `hunter-sales` as active sales sub-lanes.

## Decision Summary

Do not add new top-level wiki domains yet.

The current schema is still structurally correct for the first synthesis pass: `sales`, `design`, `equipment`, `projects`, `service`, `company`, `governance`, and `knowledge-base` remain usable homes. Adding new folders now would create structure before there is enough compiled page density to justify the maintenance cost.

The strongest domain-expansion signal is `order-execution`. The first compiled pages now live under `projects` and `governance` with clear `order-execution` tags and links, and FSCR-011 now adds evaluation fixture discipline under governance. Reassess a dedicated `wiki/order-execution/` domain only after the compiled pages create enough repeated navigation, ownership, state-boundary, or evaluation-boundary explanation to justify the maintenance cost.

The broader structure review is recorded in [[information-architecture-pressure-test|Information Architecture Pressure Test]]. That page keeps the physical folders stable for now but changes the operating rule: use lifecycle, agent-capability, and readiness/state maps as primary navigation lenses, then land pages in the least-bad current storage folder until migration triggers are met.

## Candidate Decisions

| Candidate | Current Decision | Home For Now | Evidence | Promotion Trigger |
| --- | --- | --- | --- | --- |
| `order-execution` | Active synthesis lane, but not a top-level domain yet. | `wiki/projects/` for order-readiness and execution workflow pages; `wiki/governance/` for gate rules, human review boundaries, evaluation patterns, and fixture discipline. | FSCR-008 shows closed-won, order-ready, delivery-ready, install-complete, and relationship-ready as distinct states. FSCR-009 and FSCR-010 are synthesized into readiness, state-model, and gate-rule pages. FSCR-011 is synthesized into an evaluation-fixture governance page without importing the upstream machine-readable fixture bundle. | Create `wiki/order-execution/` only if the pages make `projects` and `governance` navigation too broad or force repeated cross-domain explanations. |
| `operating-model` | Keep as a canonical lens, not a new domain. | `wiki/company/commercial-fitness-distributor-operating-model.md`, linked from root and workflow pages. | FSCR-002 and FSCR-003 establish the parent lifecycle and data-object spine, but the current page works as the parent map without a new folder. | Promote only if separate lifecycle, role, value-stream, and data-object pages become hard to maintain inside `company` and `knowledge-base`. |
| `agent-workflows` | Keep as a knowledge-base answerability and bridge lens. | `wiki/knowledge-base/agent-capability-map.md`, `wiki/knowledge-base/wiki-to-agent-build-bridge.md`, and future knowledge-base pages about agent navigation, boundaries, and build bridges. | FSCR-006 identifies capability clusters across domains, and FSCR-013 now supplies a build-bridge pattern. These are not final product agents and should not be named as a product surface too early. | Promote only after multiple compiled pages need a shared home for agent workflow contracts rather than domain workflow content. |
| `lead-intelligence` or `prospecting` | Active sales sub-lanes, but not a top-level domain yet. | `wiki/sales/source-aware-lead-intake-routing.md`, `wiki/sales/lead-to-closed-won-workflow.md`, and `wiki/sales/hunter-sales-existing-multifamily-pattern.md`. | FSCR-016 gives source-aware lead intake a compiled workflow page, while FSCR-012 now has a hunter-sales validation-status checkpoint, a dealer-backed Regency active-workflow duplicate-block capture, and a soft-negative split-candidate capture. Remaining probes stay provisional. | Reassess after source-aware lead intake, lead qualification, lead research, hunter sales, and source-quality learning have multiple validated compiled pages and repeated navigation pressure. |
| `quote-readiness`, `pricing-readiness`, or `freight-install` | Active sales readiness sub-lane, but not a top-level domain yet. | `wiki/sales/freight-install-quote-readiness.md`, with links to `projects`, `governance`, and `equipment`. | FSCR-017 creates one compiled F&I quote-readiness page that bridges quote/proposal readiness to order-execution handoff. It does not yet cover the full pricing, margin, tax, financing, proposal, or product/source-freshness family. | Reassess only after multiple validated quote-readiness pages create repeated navigation, ownership, review-boundary, or source-freshness pressure. |
| `installed-base` | Defer as a lifecycle lens across service, equipment, and sales. | `wiki/service/`, `wiki/equipment/`, and relationship-continuity sections until sourced service/warranty pages exist. | The operating model says installed assets matter, but the current compiled evidence is strategic rather than enough for durable rules. | Reassess after service, warranty, parts, replacement, or post-install relationship pages are sourced. |

## Domain Pressure Recheck 2026-06-27

Recheck result: no new top-level domain yet.

The current pressure is real enough to preserve named lanes, but not strong enough to create new folders:

- `order-execution` now has four compiled pages plus the close-won-to-delivery workflow. The split is still readable: `projects` owns state, readiness behavior, owners, and handoffs; `governance` owns blockers, warnings, review boundaries, overrides, evaluation expectations, and fixture discipline.
- `source-aware lead intake` now has one compiled target-state page under `sales`, and `hunter-sales` has one compiled design-hypothesis page with a validation-status checkpoint plus a dealer-backed Regency active-workflow capture. A top-level `lead-intelligence` or `prospecting` domain would still make provisional or early-stage patterns look more settled than they are.
- `freight/install quote readiness` now has one compiled target-state page under `sales`. A top-level `quote-readiness`, `pricing`, or `freight-install` domain would overstate the lane because current rules, owner thresholds, actual-cost variance, and broader pricing/proposal pages are not validated yet.
- `installed-base` appears as a relationship-ready and service-lifecycle concern, but the wiki does not yet have sourced warranty, parts, service, replacement, or post-install relationship pages. Keep it as a lifecycle lens until those pages exist.
- `agent-workflows` and `operating-model` still work as lenses because the current pages are maps, capability summaries, and bridge guidance, not separate page families with their own maintenance needs.

Promotion should require more than repeated tags. A new top-level domain should be created only when the current homes force repeated navigation explanations, unclear ownership boundaries, or multiple validated pages that need shared structure.

## Current Order-Execution Lane

The order-execution lane now has three compiled pages without changing the top-level schema:

- [[../projects/order-execution-readiness-agent-requirements|Order Execution Readiness Agent Requirements]].
- [[../projects/order-execution-state-model|Order Execution State Model]].
- [[../governance/order-execution-transition-gate-rules|Order Execution Transition Gate Rules]].
- [[../governance/agent-evaluation-fixtures|Agent Evaluation Fixtures]].

These pages preserve the domain split:

- `projects` explains workflow state, readiness behavior, owners, and handoffs.
- `governance` explains blocker/warning policy, review boundaries, overrides, evaluation expectations, synthetic-fixture discipline, and trace requirements.

## Current Source-Aware Lead Intake Lane

The source-aware lead intake lane now has one compiled target-state page under `sales`:

- [[../sales/source-aware-lead-intake-routing|Source-Aware Lead Intake And Routing]].

This page strengthens source-intelligence, lead-routing, lead-research, and outcome-tracking answerability without creating a top-level domain. Its source family includes roadmap capability, taxonomy, data-model, research/enrichment, and case-study artifacts, so the correct domain decision is to keep the lane inside `sales` until more validated pages create stronger structure pressure.

## Current Hunter-Sales Lane

The hunter-sales lane now has one compiled design-hypothesis page under `sales`:

- [[../sales/hunter-sales-existing-multifamily-pattern|Hunter Sales Existing Multifamily Pattern]].

This page strengthens prospecting and lead-intelligence answerability without creating a top-level domain. The validation-status checkpoint confirms that real/sanitized examples support source-origin routing, service-to-sales review, grouped-property mapping, and active-workflow duplicate blocking. The dealer-backed Regency capture now anchors duplicate-outreach blocking when outbound response becomes active site visit, proposal, bid-collection, approved quote, closed-won, or order-readiness work. The soft-negative split-candidate capture clarifies response-classification needs, but no remaining provisional probe was promoted to dealer-confirmed or build-ready policy. The correct domain decision is still to keep the lane inside `sales` until validated examples create stronger structure pressure.

## Current Freight And Install Quote-Readiness Lane

The freight/install quote-readiness lane now has one compiled target-state page under `sales`:

- [[../sales/freight-install-quote-readiness|Freight And Install Quote Readiness]].

This page strengthens quote/proposal readiness without creating a top-level domain. Its source family crosses sales, projects, governance, and equipment, but its immediate business decision is whether freight, install, or extraction assumptions are safe enough for customer-facing quote use. The correct domain decision is to keep it in `sales` while linking to order-execution state, transition gate rules, and upstream equipment/source-freshness dependencies.

## Current Wiki-To-Agent Build Bridge Lane

The wiki-to-agent build bridge now has one compiled reference-pattern page under `knowledge-base`:

- [[wiki-to-agent-build-bridge|Wiki To Agent Build Bridge]].

This page strengthens the `agent-workflows` lens without creating a top-level domain. Its purpose is to govern translation from mature wiki knowledge to future build-facing requirements while explicitly avoiding product schema, agent architecture, live tooling, and implementation specs.

## Next Review Decision

The domain-pressure recheck is complete for the current page set. The next coherent slice should choose between these options:

1. Treat FSCR-011 evaluation discipline as locally synthesized in [[../governance/agent-evaluation-fixtures|Agent Evaluation Fixtures]]; do not import the upstream fixture bundle unless a future approved build lane opens that scope.
2. Use [[information-architecture-pressure-test|Information Architecture Pressure Test]] before any new folder or migration decision.
3. Continue hunter-sales validation only by capturing or synthesizing the next real/sanitized dealer example from the remaining open list, especially budget-window target review, prospecting no-response, manager-change signal quality, scoped hard stops, soft-negative response, or sensitive-account review ownership.
4. Validate source-aware lead intake with real or sanitized lead-source examples before moving it toward build-facing requirements.
5. Treat FSCR-017 as locally synthesized in [[../sales/freight-install-quote-readiness|Freight And Install Quote Readiness]]; do not import raw quote/task/pricing artifacts or open live pricing automation unless Josh explicitly opens that scope.
6. Continue the next non-gated roadmap workflow family if no dealer examples are available and no Josh-approved build/evaluation implementation lane is open.
7. Use [[wiki-to-agent-build-bridge|Wiki To Agent Build Bridge]] only as a readiness lens; do not start implementation handoff until a workflow has stronger validation and a Josh-approved build lane.

Do not re-open top-level domain promotion until new compiled pages or validation examples create fresh evidence.

## Boundaries

- Keep commercial equipment catalog/schema, equipment answerability, source manifest pattern, validation gates, and repo-boundary option work upstream in `fast-os-knowledge-base` until mature outputs are available to evaluate.
- Do not bulk-import roadmap artifacts.
- Do not promote provisional hunter-sales scenarios into durable target-state rules without preserving validation labels.
- Do not turn current Fit Supply or NetSuite evidence into the target-state answer key.

## Working Rule

Use the smallest structure that preserves meaning.

For the next pass, that means named lenses inside existing domains, not new top-level domains. If future pages repeat the same navigation, ownership, and state-boundary explanations, that repetition is the evidence needed to promote a lens into a first-class domain.
