---
title: Freight And Install Quote Readiness
type: Workflow
domain: sales
knowledge_scope: target-state
status: Draft
last_reviewed:
reviewed_by:
sources:
  - raw/imports/fast-os-capability-roadmap-source-inventory.md#fscr-017
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/05-capability-roadmap/freight-install-quote-readiness-capability-card-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/05-capability-roadmap/automated-freight-install-estimation-workflow-decomposition-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/05-capability-roadmap/lead-to-quote-workflow-decomposition-example-v1.md
  - wiki/sales/source-aware-lead-intake-routing.md
  - wiki/sales/lead-to-closed-won-workflow.md
  - wiki/order-execution/close-won-to-delivery-workflow.md
  - wiki/order-execution/order-execution-state-model.md
related:
  - [[source-aware-lead-intake-routing|Source-Aware Lead Intake And Routing]]
  - [[lead-to-closed-won-workflow|Lead To Closed Won Workflow]]
  - [[../order-execution/close-won-to-delivery-workflow|Close Won To Delivery Workflow]]
  - [[../order-execution/order-execution-state-model|Order Execution State Model]]
  - [[../order-execution/order-execution-transition-gate-rules|Order Execution Transition Gate Rules]]
  - [[../knowledge-base/distributor-workflow-map|Distributor Workflow Map]]
  - [[../knowledge-base/agent-capability-map|Agent Capability Map]]
  - [[../knowledge-base/domain-model-review|Domain Model Review]]
agent_answerability:
  - What must be known before freight, install, or extraction values are safe to include in a customer-facing quote?
  - Which F&I estimation actions can a future agent prepare, and which require human review?
  - How should approved freight/install assumptions carry into post-close order execution?
  - What source, rule, confidence, validity, and review context must be preserved for freight/install estimates?
tags:
  - sales-workflow
  - quote-readiness
  - freight-install
  - human-review
  - roadmap-derived
provenance_notes: Synthesized 2026-06-27 from the roadmap freight/install quote-readiness family as a target-state workflow page. This page does not import raw NetSuite tasks, quote PDFs, screenshots, customer names, customer pricing, or private logistics artifacts. Current freight methods, installer rules, approval ownership, estimate thresholds, and actual-cost variance still need validation before this becomes build-facing policy.
---

# Freight And Install Quote Readiness

This page captures the target-state workflow for making a customer quote freight/install ready.

The important boundary is:

```text
not "FAST OS automatically prices freight and install"
but "FAST OS helps the quote become freight/install ready, prepares reviewable estimates, routes exceptions, preserves provenance, and carries approved assumptions into handoff"
```

Freight, install, and extraction/removal values are customer-facing financial commitments. They affect quote completeness, margin, trust, delivery expectations, and post-close execution. A future agent can help a great deal, but it should not silently turn uncertain logistics or installation assumptions into quote truth.

## Source Boundary

The roadmap source family includes current workflow evidence, logistics training concepts, prior estimator thinking, and case-derived workflow examples. This compiled page preserves the workflow pattern without importing raw task screenshots, quote PDFs, private attachments, source amounts, customer pricing, or current-system records.

Treat current Fit Supply and NetSuite references as evidence for the coordination pattern, not as the target-state answer key. Treat freight and installer rules as validation needs until current authoritative artifacts are reviewed.

## Navigation Lens Classification

This synthesis family was classified through the wiki navigation lenses before choosing its storage home.

| Lens | Classification |
| --- | --- |
| Lifecycle lens | Primary stage is Quote, Pricing, Margin, and Proposal. It also depends on site/project context and carries forward into Close, Procurement, Delivery, and Install. |
| Capability lens | Strengthens quote/proposal readiness, project-context readiness, approval/handoff readiness, install readiness, and playbook governance. |
| Readiness/state lens | Defines what must be true before a quote is `quote-ready` with respect to freight, install, and extraction. Approved assumptions later become part of `order-ready`, `site-ready`, and `delivery-ready` review. |
| Evaluation/build-readiness lens | Useful as wiki knowledge and future evaluation criteria, but not ready as product schema, pricing automation, or live freight/install tooling. Current rules, thresholds, and actuals need validation first. |
| Storage-domain lens | Store in `sales` because the immediate business decision is quote readiness before customer-facing proposal output. Link to `projects`, `governance`, and `equipment` because execution, review rules, and product handling all depend on the result. |
| Domain-promotion lens | Do not create a new top-level `quote-readiness`, `pricing`, or `freight-install` domain yet. This is a sales sub-lane and cross-domain readiness pattern for now. |

## Business Outcome

Make quotes complete and trustworthy without forcing reps to become logistics or install-pricing experts.

```text
quote draft exists
-> freight/install/extraction need is detected
-> quote context is inherited before asking the rep for more information
-> missing blockers are surfaced
-> routine versus exception path is recommended
-> reviewable freight/install/extraction values are prepared or requested
-> human approval happens before customer-facing use
-> approved assumptions carry into order execution
-> actual outcomes improve future rules
```

The early value is quote-readiness and reviewable preparation, not autonomous pricing.

## Workflow Spine

| Step | Decision | Output / State | AI Posture | Human Boundary |
| --- | --- | --- | --- | --- |
| Detect F&I requirement | Does this quote need freight, install, extraction/removal, or none? | `QuoteReadinessChecklist` with F&I status. | Recommend and prepare. | Rep reviews ambiguous replacement, delivery, or scope cases. |
| Inherit quote context | What does the quote already know? | `FreightInstallInputPacket` linked to quote version. | Observe and prepare. | Rep reviews only when inherited context is ambiguous. |
| Identify missing inputs | What facts are still required to estimate responsibly? | `QuoteBlocker` or missing-context question. | Prepare targeted questions. | Rep, logistics, installer, or PM resolves critical facts. |
| Classify routine vs exception | Can rules handle this, or does a reviewer need to estimate? | Routine/exception classification and owner route. | Recommend. | Logistics/install reviewer approves edge cases. |
| Select freight path | Which freight estimating mode fits this quote? | `FreightEstimateMode`. | Recommend. | Reviewer approves low-confidence or high-impact mode choices. |
| Prepare freight estimate | What freight value is reliable enough for this quote version? | Draft `FreightEstimate` with source, assumptions, confidence, and validity window. | Prepare only. | Human approval before customer-facing use. |
| Prepare install/extraction estimate | What install or removal value is reasonable for this scope? | Draft `InstallEstimate` or `ExtractionLine`. | Prepare only. | Human approval and customer expectation review when scope is inferred. |
| Validate estimate | Are values safe for quote send, margin, and policy? | `EstimateValidationResult`. | Prepare, flag, and route. | Rep, manager, owner, logistics, or install owner approves as policy requires. |
| Preserve provenance | What source, rule, confidence, and reviewer produced the value? | `EstimateSource`, `RuleVersion`, `EstimateReviewEvent`. | Record. | Overrides require reviewer identity and reason. |
| Carry into handoff | What assumptions must operations receive after approval? | `InstallHandoffPacket` or F&I section of order-readiness packet. | Prepare. | PM/order owner reviews before execution release. |
| Learn from actuals and freshness | Did the estimate stay current and match reality? | `FreightFreshnessEvent` and `EstimateVarianceEvent`. | Observe and recommend. | Humans approve quote changes, customer resends, and rule updates. |

## Context Required

Freight/install readiness depends on several context families.

| Context Family | Why It Matters | Current Wiki Treatment |
| --- | --- | --- |
| Quote and quote version | The estimate must attach to the version the customer may receive. | Foundational target-state requirement. |
| Quote line items and product handling | Product category, quantity, dimensions, weight, options, and handling profile affect freight and install. | Keep model-specific catalog work upstream until mature outputs are available. |
| Site and delivery context | Address, dock/liftgate, access, stairs, appointment, commercial/residential status, room path, and removal scope affect reliability. | Preserve as quote blockers or site/project readiness facts. |
| Freight mode and source | Vendor-exact, recent comparable, vendor rubric, formal rating path, dummy shipment, broker request, or human review are different evidence types. | Use mode taxonomy; do not collapse to one formula. |
| Installer and extraction rules | Territory, minimums, surcharges, category, quantity, stairs, mileage, removal, and access constraints can change install value. | Needs current-policy validation before becoming rule truth. |
| Review and approval | Customer-facing financial values require human approval and audit. | Required boundary. |
| Validity and actuals | Freight can expire or vary; actual cost feedback should improve future rules. | Treat freshness and variance as learning signals, not automatic customer communication. |

## Human Review Rules

| Action | Early FAST OS Posture |
| --- | --- |
| Detect F&I requirement | Recommend automatically. |
| Inherit quote context | Prepare automatically from authorized quote context. |
| Ask missing-context questions | Prepare targeted questions and blockers. |
| Classify routine versus exception | Recommend with explanation. |
| Choose freight estimating mode | Recommend, especially when confidence or cost impact is uncertain. |
| Prepare draft freight/install/extraction values | Prepare with source, assumptions, confidence, and validity detail. |
| Use values in a customer-facing quote | Require human approval. |
| Override an estimate | Require reviewer identity, reason, and source/rule history. |
| Refresh stale freight internally | Prepare or flag for review. |
| Resend a revised quote to the customer | Require explicit rep approval. |
| Change freight/install rules from actuals | Require admin or owner review. |

## Relationship To Order Execution

Freight/install readiness sits before post-close order execution, but it should not disappear after the quote is approved.

Approved F&I assumptions should carry into:

- closed-won to order-ready review
- vendor order and ship-to path decisions
- site-ready and delivery-ready checks
- installer release and schedule planning
- extraction/removal sequencing
- completion and actual-cost variance review

This page therefore links sales quote readiness to [[../order-execution/order-execution-state-model|Order Execution State Model]].

Working rule:

```text
quote-ready means customer-facing F&I assumptions are reviewed enough to send
order-ready means accepted F&I assumptions are preserved enough for operations to act
delivery-ready means site, receiving, extraction, and installer facts are executable
```

These are related states, but they are not interchangeable.

## Wiki And Agent Implications

This page strengthens these capability clusters in [[../knowledge-base/agent-capability-map|Agent Capability Map]]:

- project-context readiness
- quote and proposal readiness
- approval and handoff readiness
- order coordination
- install readiness
- playbook governance

It also clarifies a schema lesson without defining implementation schema:

```text
the estimate number is not enough
```

The system also needs source, mode, assumptions, confidence, quote version, validity window, reviewer, override reason, and downstream handoff context.

## Open Validation Needs

- Which current freight and installer artifacts are authoritative enough to model first?
- Who owns freight and install review today: logistics, install coordinator, operations, owner, vendor, installer partner, or sales manager?
- Which product categories are routine enough for early preparation?
- Which freight modes should be supported first?
- Which site/access details should block draft estimation until confirmed?
- How should freight/install/extraction appear to the customer: separate lines, grouped lines, or both?
- Which confidence, dollar, margin, or risk thresholds require extra review?
- How often do actual freight/install costs materially differ from quoted values?
- Should stale freight monitoring be internal-only by default, or sometimes recommend customer-facing quote revision?
- Should future exception routing create NetSuite tasks during transition, or use a separate FAST OS review queue?

Do not move this page toward product requirements until those validation questions have stronger source-backed answers.
