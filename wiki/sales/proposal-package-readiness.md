---
title: Proposal Package Readiness
type: Workflow
domain: sales
knowledge_scope: target-state
status: Draft
last_reviewed:
reviewed_by:
sources:
  - raw/imports/fast-os-capability-roadmap-source-inventory.md#fscr-018
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/05-capability-roadmap/regency-proposal-workflow-cross-repo-synthesis-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/05-capability-roadmap/lead-to-quote-workflow-decomposition-example-v1.md
  - raw/imports/fast-os-capability-roadmap/regency-lead-to-closed-won-work-unit-decomposition-v1.md
  - wiki/sales/lead-to-closed-won-workflow.md
  - wiki/sales/freight-install-quote-readiness.md
related:
  - [[source-aware-lead-intake-routing|Source-Aware Lead Intake And Routing]]
  - [[lead-to-closed-won-workflow|Lead To Closed Won Workflow]]
  - [[freight-install-quote-readiness|Freight And Install Quote Readiness]]
  - [[../order-execution/close-won-to-delivery-workflow|Close Won To Delivery Workflow]]
  - [[../knowledge-base/distributor-workflow-map|Distributor Workflow Map]]
  - [[../knowledge-base/agent-capability-map|Agent Capability Map]]
  - [[../knowledge-base/domain-model-review|Domain Model Review]]
  - [[../design/index|Design]]
  - [[../projects/index|Projects]]
agent_answerability:
  - When is a proposal package ready for customer-facing use?
  - What project, room, design, visual, quote, and vendor context must be reviewed before proposal assembly?
  - Which proposal-preparation actions can a future agent prepare, and which customer-facing decisions require human approval?
tags:
  - sales-workflow
  - proposal-readiness
  - project-context
  - human-review
  - roadmap-derived
provenance_notes: Synthesized 2026-06-27 from the sanitized Regency proposal workflow cross-repo synthesis and lead-to-quote roadmap example. This page does not import raw customer folders, quote PDFs, photos, pricing, contact details, generated proposal assets, or presentation-builder source artifacts. It preserves proposal-readiness workflow learning as target-state wiki knowledge, not product implementation, autonomous visual generation, or customer-facing proposal tooling.
---

# Proposal Package Readiness

This page captures the target-state workflow for turning project context, room context, design assets, quote inputs, visuals, and commercial review into a proposal package that is safe for customer-facing use.

The important boundary is:

```text
not "FAST OS automatically generates the proposal"
but "FAST OS helps decide whether the project context and proposal package are ready enough for a human-reviewed customer-facing output"
```

Proposal work is where design, product fit, commercial terms, visual trust, and relationship judgment meet. A future agent can prepare and check the package, but the rep remains responsible for what is sent to the customer.

## Source Boundary

The primary source is a sanitized roadmap synthesis of earlier presentation-builder workflow work. It summarizes workflow learning without copying raw customer folders, quote PDFs, photos, pricing, contact details, generated proposal assets, or presentation-builder files into this repo.

Treat ECDESIGN, PowerPoint, vendor tools, quote PDFs, and generated visuals as source or asset systems whose outputs need review. Do not treat this page as permission to build a proposal generator, ingest raw project folders, or replace trusted design tools.

## Navigation Lens Classification

This synthesis family was classified through the wiki navigation lenses before choosing its storage home.

| Lens | Classification |
| --- | --- |
| Lifecycle lens | Primary stage is Proposal Assembly. It depends on Discovery, Site Survey, Layout and Design, Equipment Selection, Pricing and Quote Creation, and carries into Follow-Up, Close, and Order Execution. |
| Capability lens | Strengthens project-context readiness, site-visit debrief, room-context capture, solution design support, quote/proposal readiness, visual accuracy review, and follow-up state tracking. |
| Readiness/state lens | Defines a `proposal-ready` state: the quote version, proposal assets, room/design context, visuals, vendor branches, assumptions, recipient, and message are reviewed enough for human-approved customer-facing delivery. |
| Evaluation/build-readiness lens | Useful as wiki knowledge and future evaluation criteria, but not ready as product schema, autonomous layout generation, visual generation, interactive proposal tooling, or proposal-send automation. |
| Storage-domain lens | Store in `sales` because the immediate business decision is a customer-facing sales proposal. Link to `design`, `projects`, `order-execution`, and `governance` because room context, handoff, and review discipline all affect the proposal. |
| Domain-promotion lens | Do not create a top-level `quote-readiness`, `proposal-readiness`, or `workflows` domain yet. This is a sales readiness page and cross-domain workflow lens for now. |

## Business Outcome

Make proposal packages persuasive, accurate enough, and reviewable without turning incomplete field material or polished visuals into false confidence.

```text
site and project context exists
-> room facts and uncertainty are preserved
-> design and visual assets are reviewed against source context
-> quote, F&I, trade-in, flooring, terms, and vendor branches are aligned
-> proposal package is assembled as a draft
-> human approval happens before customer-facing delivery
-> delivery and follow-up state are recorded
```

The early value is readiness checking and package preparation, not autonomous proposal creation.

## Workflow Spine

| Step | Decision | Output / State | AI Posture | Human Boundary |
| --- | --- | --- | --- | --- |
| Assess project-context readiness | Is there enough site, buyer, room, and scope context to start proposal assembly? | `ProjectContextReadiness` or missing-context list. | Prepare and flag gaps. | Rep confirms whether the opportunity is ready for proposal work. |
| Preserve room context and uncertainty | Which room facts are known, uncertain, or still need confirmation? | `RoomContext`, `MeasurementSet`, `Constraint`, `Unknown`, and `ConfirmationQuestion`. | Structure notes and ask debrief questions. | Rep or designer confirms facts before reliance. |
| Separate existing equipment and removal scope | What existing assets, trade-in items, or extraction assumptions affect the proposal? | `ExistingEquipmentInventory`, `TradeInItem`, `RemovalScope`, or review question. | Prepare inventory and dependencies. | Rep, trade-in owner, or operations reviewer confirms commercial treatment. |
| Check design asset readiness | Are layout, line drawing, ECDESIGN, rendering, and spec assets source-aligned enough to use? | `DesignPackage`, `LayoutAsset`, visual readiness flags. | Inventory and compare assets. | Rep/designer approves visual and layout use. |
| Validate commercial package | Does the package match the approved quote version, F&I assumptions, terms, specs, vendor scope, and recipient? | `ProposalReadinessChecklist`. | Prepare checklist and draft package. | Rep approves price, scope, promises, and customer-facing claims. |
| Review visuals and claims | Could visuals, renderings, or proposal language mislead the customer? | `VisualAccuracyReview` and disclaimer needs. | Flag mismatches and unsupported claims. | Human approves visuals and disclaimers. |
| Assemble proposal draft | What package should be sent, and what message should frame it? | Draft `ProposalPackage` and `ProposalDeliveryDraft`. | Assemble and draft. | Rep approves before send. |
| Validate interactive or web version | If a web proposal exists, does it match the approved quote and source package? | Proposal parity check. | Compare and flag drift. | Human approves any customer-facing web output. |
| Record delivery and follow-up state | What was sent, to whom, and what happens next? | `ProposalDeliveryEvent`, `FollowUpState`, and task. | Record, remind, and draft follow-up. | Rep owns relationship-sensitive follow-up. |

## Context Required

Proposal readiness depends on several context families.

| Context Family | Why It Matters | Current Wiki Treatment |
| --- | --- | --- |
| Site and room context | Measurements, photos, sketches, constraints, zones, and unknowns determine whether design and quote work are trustworthy. | Preserve uncertainty; do not convert rough field material into false precision. |
| Existing equipment and removal context | Trade-in, extraction, disposal, and replacement scope affect price, install, customer expectations, and handoff. | Prepare dependencies with review. |
| Design and visual assets | Layouts, line drawings, ECDESIGN renderings, and photoreal visuals help explain the proposal but can mislead if source alignment is weak. | Treat visuals as reviewed proposal assets, not factual proof by themselves. |
| Quote and quote version | The proposal must match the quote version, F&I assumptions, terms, discounts, specs, and approved scope. | Link to [[freight-install-quote-readiness|Freight And Install Quote Readiness]] for F&I review. |
| Vendor and branch scope | Flooring, vendor quotes, trade-in values, or third-party scope can drift from dealer-controlled proposal scope. | Keep branches explicit until reviewed. |
| Recipient and buyer path | The proposal send target, procurement process, bid collection, and approval path affect framing and follow-up. | Track as proposal delivery and follow-up state. |
| Trust and provenance | Every customer-facing claim should be backed by a source, review, or explicit assumption. | Preserve review events and source links. |

## Human Review Rules

| Action | Early FAST OS Posture |
| --- | --- |
| Inventory available project and proposal assets | Observe and prepare. |
| Convert field notes into room context | Draft with uncertainty and confirmation questions. |
| Interpret ambiguous dimensions or constraints | Require rep or designer review. |
| Suggest proposal-positioning notes | Recommend with rationale. |
| Select final product mix or package level | Require rep approval. |
| Prepare proposal checklist and draft package | Prepare only. |
| Use photorealistic or enhanced visuals | Require human review against quote, room context, and source rendering. |
| Publish or send an interactive/web proposal | Require explicit human approval and quote/proposal parity check. |
| Send the proposal or customer-facing message | Require rep approval. |
| Track delivery and follow-up state | Record and recommend; rep owns relationship-sensitive action. |

## Relationship To Existing Pages

[[lead-to-closed-won-workflow|Lead To Closed Won Workflow]] keeps the broader Regency sales path from lead signal through approval and order-readiness boundary. This page deepens the proposal assembly portion of that workflow.

[[freight-install-quote-readiness|Freight And Install Quote Readiness]] owns the F&I slice of quote readiness. This page treats approved F&I assumptions as one part of the larger customer-facing proposal package.

[[../order-execution/close-won-to-delivery-workflow|Close Won To Delivery Workflow]] begins after approval and closed-won. Proposal readiness should preserve the assumptions that later become order-readiness input, but proposal-ready is not the same as order-ready.

Working rule:

```text
project-context-ready means enough reviewed source context exists to assemble the package
proposal-ready means the customer-facing package is reviewed enough to send
order-ready means accepted proposal assumptions are preserved enough for operations to act
```

These states are related, but they are not interchangeable.

## Wiki And Agent Implications

This page strengthens these capability clusters in [[../knowledge-base/agent-capability-map|Agent Capability Map]]:

- site-visit capture and debrief
- project-context readiness
- solution design support
- quote and proposal readiness
- follow-up and decision-state
- approval and handoff readiness

It also clarifies a recurring schema lesson without defining implementation schema:

```text
the proposal file is not enough
```

The system also needs source context, room facts, uncertainty, design assets, approved quote version, visual review, vendor branches, recipient, delivery event, follow-up state, and handoff assumptions.

## Open Validation Needs

- Which proposal assets should be considered authoritative for each project type?
- What minimum room context is required before layout or visual assets can be used in a proposal?
- Which visual errors are common enough to become checklist items?
- When should enhanced photorealistic visuals be allowed, disclaimed, or avoided?
- How should interactive/web proposals stay synchronized with approved quotes and PDFs?
- What proposal-positioning factors should be captured when the customer gives no budget?
- Which vendor quote branches belong in the proposal package versus internal review only?
- What recipient and buyer-path states should drive follow-up timing?
- Which proposal-readiness checks are universal, and which depend on segment, project size, or rep judgment?

Do not move this page toward product requirements until those validation questions have stronger source-backed answers.
