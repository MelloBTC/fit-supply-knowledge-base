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
  - wiki/sales/source-aware-lead-intake-routing.md
  - wiki/sales/lead-to-closed-won-workflow.md
  - wiki/sales/hunter-sales-existing-multifamily-pattern.md
  - wiki/projects/close-won-to-delivery-workflow.md
  - wiki/projects/order-execution-readiness-agent-requirements.md
  - wiki/projects/order-execution-state-model.md
  - wiki/governance/order-execution-transition-gate-rules.md
related:
  - [[roadmap-import-plan|Roadmap Import Plan]]
  - [[agent-answerability-targets|Agent Answerability Targets]]
  - [[wiki-to-agent-build-bridge|Wiki To Agent Build Bridge]]
  - [[distributor-workflow-map|Distributor Workflow Map]]
  - [[agent-capability-map|Agent Capability Map]]
  - [[../company/commercial-fitness-distributor-operating-model|Commercial Fitness Distributor Operating Model]]
  - [[../sales/source-aware-lead-intake-routing|Source-Aware Lead Intake And Routing]]
  - [[../sales/lead-to-closed-won-workflow|Lead To Closed Won Workflow]]
  - [[../sales/hunter-sales-existing-multifamily-pattern|Hunter Sales Existing Multifamily Pattern]]
  - [[../projects/close-won-to-delivery-workflow|Close Won To Delivery Workflow]]
  - [[../projects/order-execution-readiness-agent-requirements|Order Execution Readiness Agent Requirements]]
  - [[../projects/order-execution-state-model|Order Execution State Model]]
  - [[../governance/order-execution-transition-gate-rules|Order Execution Transition Gate Rules]]
agent_answerability:
  - Should this wiki create a new top-level domain or keep a concept inside the current domain model?
  - Which roadmap-derived concept should become the next synthesis lane?
  - What evidence would justify promoting a workflow lens into a first-class domain?
tags:
  - domain-model
  - roadmap-derived
  - wiki-maintenance
provenance_notes: Domain review checkpoint based on the first roadmap synthesis pass and source inventory. Updated 2026-06-27 with pressure rechecks after order-execution, source-aware lead intake, hunter-sales synthesis, FSCR-013 bridge closure, the hunter-sales validation-status checkpoint, and the dealer-backed Regency active-workflow capture. This page records wiki structure decisions, not current Fit Supply operating facts.
---

# Domain Model Review

This page records the first domain model review after the initial roadmap synthesis pass, plus a pressure recheck after the order-execution and hunter-sales synthesis lanes were added.

The review question is whether the starter wiki domains should expand before more roadmap artifacts are synthesized. The short answer is: keep the top-level domain model stable for now, treat `order-execution` as an active workflow lens, and treat `source-intelligence`, `lead-intake`, and `hunter-sales` as active sales sub-lanes.

## Decision Summary

Do not add new top-level wiki domains yet.

The current schema is still structurally correct for the first synthesis pass: `sales`, `design`, `equipment`, `projects`, `service`, `company`, `governance`, and `knowledge-base` remain usable homes. Adding new folders now would create structure before there is enough compiled page density to justify the maintenance cost.

The strongest domain-expansion signal is `order-execution`. The first compiled pages now live under `projects` and `governance` with clear `order-execution` tags and links. Reassess a dedicated `wiki/order-execution/` domain only after the new pages create enough repeated navigation, ownership, or state-boundary explanation to justify the maintenance cost.

## Candidate Decisions

| Candidate | Current Decision | Home For Now | Evidence | Promotion Trigger |
| --- | --- | --- | --- | --- |
| `order-execution` | Active synthesis lane, but not a top-level domain yet. | `wiki/projects/` for order-readiness and execution workflow pages; `wiki/governance/` for gate rules, human review boundaries, and evaluation patterns. | FSCR-008 shows closed-won, order-ready, delivery-ready, install-complete, and relationship-ready as distinct states. FSCR-009 and FSCR-010 are now synthesized into readiness, state-model, and gate-rule pages. FSCR-011 remains the evaluation-fixture follow-on. | Create `wiki/order-execution/` only if the new pages make `projects` and `governance` navigation too broad or force repeated cross-domain explanations. |
| `operating-model` | Keep as a canonical lens, not a new domain. | `wiki/company/commercial-fitness-distributor-operating-model.md`, linked from root and workflow pages. | FSCR-002 and FSCR-003 establish the parent lifecycle and data-object spine, but the current page works as the parent map without a new folder. | Promote only if separate lifecycle, role, value-stream, and data-object pages become hard to maintain inside `company` and `knowledge-base`. |
| `agent-workflows` | Keep as a knowledge-base answerability and bridge lens. | `wiki/knowledge-base/agent-capability-map.md`, `wiki/knowledge-base/wiki-to-agent-build-bridge.md`, and future knowledge-base pages about agent navigation, boundaries, and build bridges. | FSCR-006 identifies capability clusters across domains, and FSCR-013 now supplies a build-bridge pattern. These are not final product agents and should not be named as a product surface too early. | Promote only after multiple compiled pages need a shared home for agent workflow contracts rather than domain workflow content. |
| `lead-intelligence` or `prospecting` | Active sales sub-lanes, but not a top-level domain yet. | `wiki/sales/source-aware-lead-intake-routing.md`, `wiki/sales/lead-to-closed-won-workflow.md`, and `wiki/sales/hunter-sales-existing-multifamily-pattern.md`. | FSCR-016 gives source-aware lead intake a compiled workflow page, while FSCR-012 now has a hunter-sales validation-status checkpoint, a dealer-backed Regency active-workflow duplicate-block capture, and a soft-negative split-candidate capture. Remaining probes stay provisional. | Reassess after source-aware lead intake, lead qualification, lead research, hunter sales, and source-quality learning have multiple validated compiled pages and repeated navigation pressure. |
| `installed-base` | Defer as a lifecycle lens across service, equipment, and sales. | `wiki/service/`, `wiki/equipment/`, and relationship-continuity sections until sourced service/warranty pages exist. | The operating model says installed assets matter, but the current compiled evidence is strategic rather than enough for durable rules. | Reassess after service, warranty, parts, replacement, or post-install relationship pages are sourced. |

## Domain Pressure Recheck 2026-06-27

Recheck result: no new top-level domain yet.

The current pressure is real enough to preserve named lanes, but not strong enough to create new folders:

- `order-execution` now has three compiled pages plus the close-won-to-delivery workflow. The split is still readable: `projects` owns state, readiness behavior, owners, and handoffs; `governance` owns blockers, warnings, review boundaries, overrides, and evaluation expectations.
- `source-aware lead intake` now has one compiled target-state page under `sales`, and `hunter-sales` has one compiled design-hypothesis page with a validation-status checkpoint plus a dealer-backed Regency active-workflow capture. A top-level `lead-intelligence` or `prospecting` domain would still make provisional or early-stage patterns look more settled than they are.
- `installed-base` appears as a relationship-ready and service-lifecycle concern, but the wiki does not yet have sourced warranty, parts, service, replacement, or post-install relationship pages. Keep it as a lifecycle lens until those pages exist.
- `agent-workflows` and `operating-model` still work as lenses because the current pages are maps, capability summaries, and bridge guidance, not separate page families with their own maintenance needs.

Promotion should require more than repeated tags. A new top-level domain should be created only when the current homes force repeated navigation explanations, unclear ownership boundaries, or multiple validated pages that need shared structure.

## Current Order-Execution Lane

The order-execution lane now has three compiled pages without changing the top-level schema:

- [[../projects/order-execution-readiness-agent-requirements|Order Execution Readiness Agent Requirements]].
- [[../projects/order-execution-state-model|Order Execution State Model]].
- [[../governance/order-execution-transition-gate-rules|Order Execution Transition Gate Rules]].

These pages preserve the domain split:

- `projects` explains workflow state, readiness behavior, owners, and handoffs.
- `governance` explains blocker/warning policy, review boundaries, overrides, and evaluation expectations.

## Current Source-Aware Lead Intake Lane

The source-aware lead intake lane now has one compiled target-state page under `sales`:

- [[../sales/source-aware-lead-intake-routing|Source-Aware Lead Intake And Routing]].

This page strengthens source-intelligence, lead-routing, lead-research, and outcome-tracking answerability without creating a top-level domain. Its source family includes roadmap capability, taxonomy, data-model, research/enrichment, and case-study artifacts, so the correct domain decision is to keep the lane inside `sales` until more validated pages create stronger structure pressure.

## Current Hunter-Sales Lane

The hunter-sales lane now has one compiled design-hypothesis page under `sales`:

- [[../sales/hunter-sales-existing-multifamily-pattern|Hunter Sales Existing Multifamily Pattern]].

This page strengthens prospecting and lead-intelligence answerability without creating a top-level domain. The validation-status checkpoint confirms that real/sanitized examples support source-origin routing, service-to-sales review, grouped-property mapping, and active-workflow duplicate blocking. The dealer-backed Regency capture now anchors duplicate-outreach blocking when outbound response becomes active site visit, proposal, bid-collection, approved quote, closed-won, or order-readiness work. The soft-negative split-candidate capture clarifies response-classification needs, but no remaining provisional probe was promoted to dealer-confirmed or build-ready policy. The correct domain decision is still to keep the lane inside `sales` until validated examples create stronger structure pressure.

## Current Wiki-To-Agent Build Bridge Lane

The wiki-to-agent build bridge now has one compiled reference-pattern page under `knowledge-base`:

- [[wiki-to-agent-build-bridge|Wiki To Agent Build Bridge]].

This page strengthens the `agent-workflows` lens without creating a top-level domain. Its purpose is to govern translation from mature wiki knowledge to future build-facing requirements while explicitly avoiding product schema, agent architecture, live tooling, and implementation specs.

## Next Review Decision

The domain-pressure recheck is complete for the current page set. The next coherent slice should choose between these options:

1. Review FSCR-011 if the next priority is evaluation discipline for order-execution gates.
2. Continue hunter-sales validation only by capturing or synthesizing the next real/sanitized dealer example from the remaining open list, especially budget-window target review, prospecting no-response, manager-change signal quality, scoped hard stops, soft-negative response, or sensitive-account review ownership.
3. Validate source-aware lead intake with real or sanitized lead-source examples before moving it toward build-facing requirements.
4. Continue the next non-gated roadmap workflow family if no dealer examples are available and evaluation discipline is not the priority.
5. Use [[wiki-to-agent-build-bridge|Wiki To Agent Build Bridge]] only as a readiness lens; do not start implementation handoff until a workflow has stronger validation and a Josh-approved build lane.

Do not re-open top-level domain promotion until new compiled pages or validation examples create fresh evidence.

## Boundaries

- Keep commercial equipment catalog/schema, equipment answerability, source manifest pattern, validation gates, and repo-boundary option work upstream in `fast-os-knowledge-base` until mature outputs are available to evaluate.
- Do not bulk-import roadmap artifacts.
- Do not promote provisional hunter-sales scenarios into durable target-state rules without preserving validation labels.
- Do not turn current Fit Supply or NetSuite evidence into the target-state answer key.

## Working Rule

Use the smallest structure that preserves meaning.

For the next pass, that means named lenses inside existing domains, not new top-level domains. If future pages repeat the same navigation, ownership, and state-boundary explanations, that repetition is the evidence needed to promote a lens into a first-class domain.