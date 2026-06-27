---
title: Close Won To Delivery Workflow
type: Workflow
domain: projects
knowledge_scope: target-state
status: Draft
last_reviewed:
reviewed_by:
sources:
  - raw/imports/fast-os-capability-roadmap-source-inventory.md#fscr-008
  - raw/imports/fast-os-capability-roadmap/regency-close-won-to-delivery-workflow-decomposition-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/06-agent-workflow-decomposition/regency-close-won-to-delivery-workflow-decomposition-v1.md
related:
  - [[../sales/lead-to-closed-won-workflow|Lead To Closed Won Workflow]]
  - [[../sales/freight-install-quote-readiness|Freight And Install Quote Readiness]]
  - [[../knowledge-base/distributor-workflow-map|Distributor Workflow Map]]
  - [[../knowledge-base/agent-capability-map|Agent Capability Map]]
  - [[../company/commercial-fitness-distributor-operating-model|Commercial Fitness Distributor Operating Model]]
agent_answerability:
  - What should happen after a quote is approved but before delivery and installation are complete?
  - What separates closed-won, order-ready, delivery-ready, install-complete, and relationship-ready?
  - Which post-close coordination tasks can AI prepare, and which require human review?
tags:
  - project-workflow
  - order-execution
  - case-backed
  - regency
  - roadmap-derived
provenance_notes: Synthesized from sanitized Regency roadmap artifact FSCR-008. Current Fit Supply and NetSuite references are treated as current-state evidence only, not as the target workflow design.
---

# Close Won To Delivery Workflow

This page captures the target-state workflow from approved customer commitment through delivery, installation completion, and relationship-management transition.

The first source is the Regency close-won-to-delivery decomposition. It uses current Fit Supply and NetSuite workflow evidence, but this page designs around the business outcome rather than copying current screens or operational sequence.

## Business Outcome

Move from approved customer commitment to completed, documented, relationship-ready installation.

```text
approved customer commitment
-> clean order handoff
-> payment and vendor coordination
-> site readiness
-> delivery and installation readiness
-> install completion evidence
-> relationship continuity
```

The strongest product read from the source is that post-close project management is coordination-heavy, mechanical, and relationship-sensitive. Future agents should automate mechanical tracking and preparation while preserving human review for payment, customer commitments, vendor actions, delivery readiness, and relationship moments.

## Design Boundary

Current-state systems are evidence, not the target design. The target-state workflow should separate several states that are easy to collapse:

| State | Meaning |
| --- | --- |
| Closed-won | Customer commitment appears real enough to end the sales opportunity stage. |
| Order-ready | Approval, quote version, order context, site/project facts, payment terms, and blocker review are sufficient for operations to act. |
| Delivery-ready | Site survey, equipment receiving status, layout, access, customer contact, and installer requirements are sufficient for delivery/install planning. |
| Install-complete | Completion photos, customer signoff, delivery confirmation, notes, and exceptions are captured and reviewed. |
| Relationship-ready | Completion is accepted or exceptions are routed, installed-base context exists, and rep/customer follow-up can begin. |

## Workflow Loop

```text
approval proof arrives
-> order-readiness context is validated
-> missing information is surfaced and routed
-> human approves handoff
-> invoice milestone and vendor PO packages are prepared
-> humans approve financial documents and vendor commitments
-> vendor acknowledgments, lead times, payment status, and blockers are tracked
-> site survey and delivery readiness are collected
-> project manager and sales rep stay in sync
-> customer status updates are generated for review or policy-bound send
-> receiving and install scheduling are coordinated
-> installation company submits completion evidence
-> completion, exceptions, installed assets, and relationship follow-up triggers are recorded
```

## Work Unit Groups

| Group | Source Work Units | Recurring Decision | Required Context | Output / State | AI Posture | Human Boundary |
| --- | --- | --- | --- | --- | --- | --- |
| Approval and order readiness | CW-01 to CW-03 | Is commitment valid, and is sold scope complete enough to move forward? | Approval artifact, accepted quote version, PO/contract terms, site/project context, F&I, trade-in, flooring, layout, custom details. | `ApprovalProof`, `PurchaseOrderReview`, `OrderReadinessChecklist`, `OrderReadinessState`, `OrderBlocker`. | Observe, compare, highlight, prepare checklist, and route gaps. | Sales/order owner confirms commitment; PM or order owner releases handoff. |
| Payment and vendor procurement | CW-04 to CW-06 | What payment terms apply, which vendor POs are needed, and what lead times should the team expect? | Customer terms, invoice milestones, quote lines, vendor split, SKUs, quantities, lead times, vendor acknowledgments. | `InvoiceMilestonePlan`, `VendorPOPackage`, `VendorPurchaseOrder`, `LeadTimeStatusUpdate`. | Prepare packages, track status, and draft internal updates. | Accounting/purchasing/PM approves financial and vendor commitments. |
| Customer and relationship-sensitive updates | CW-07, CW-07A, CW-12 | What should the customer or sales rep know now, and does the issue require relationship judgment? | Payment status, lead times, schedule constraints, bad news, substitution, scope/cost/margin impact, account relationship context. | `CustomerStatusUpdate`, `SalesDecisionRequest`, `RepVisibilityUpdate`. | Draft, summarize, and route. | PM reviews routine customer updates; sales owns relationship-sensitive choices. |
| Site and delivery readiness | CW-08 to CW-11 | Is the site, equipment, installer, and schedule ready for delivery/install? | Site survey, access path, restrictions, equipment list, approved layout, receiving confirmation, customer/installer availability. | `SiteSurvey`, `DeliveryReadinessState`, `ReceivingStatus`, `InstallSchedule`. | Request, assemble, track, and recommend. | PM/installer/customer confirms readiness and schedule. |
| Exceptions and non-standard execution | CW-10A, CW-11A, CW-14 | Should the project wait, split, substitute, change scope, stage extraction, or handle punch-list/damage? | Affected item, backorder, substitution option, flooring dependency, extraction/trade-in line, install trip cost, damage/missing evidence, vendor response. | `SubstitutionDecision`, `BackorderResolution`, `ExtractionSequenceDecision`, `Exception`, `PunchListItem`. | Detect, prepare decision summary, monitor, and route. | Sales owns customer-facing choice when cost/trust is affected; PM owns execution coordination. |
| Completion and relationship continuity | CW-13 to CW-15 | Is the install complete and accepted, and what follow-up should begin? | Completion photos, customer signature, delivery confirmation, notes, serial fields, exceptions, account ownership. | `InstallationCompletionPacket`, `DeliveryConfirmation`, `RelationshipManagementTrigger`, `InstalledBaseLifecycleTrigger`. | Request, monitor, organize, and recommend follow-up. | PM validates completion; rep reviews relationship cadence. |

## Context To Preserve

- Approval artifact, signer/customer, accepted quote version, and approval date.
- PO or contract terms and mismatches against accepted quote.
- Quote/sold scope, revision history, exclusions, exceptions, and reviewed freight/install/extraction assumptions.
- Payment terms, invoice milestones, deposit/payment status, and accounting policy.
- Vendor split, POs, acknowledgments, lead times, backorders, substitutions, and shipments.
- Site survey, access path, room readiness, customer contacts, and installer requirements.
- Layouts, equipment list, receiving confirmation, and install schedule.
- Completion photos, customer signoff, delivery confirmation, punch list, damage or missing parts.
- Rep relationship context and post-install follow-up cadence.

## Risk And Autonomy

| Workflow Area | Risk Pattern | Recommended AI Role | Human Boundary |
| --- | --- | --- | --- |
| Approval and order readiness | False commitment or weak handoff creates operational false progress. | Detect likely approval, compare terms, prepare checklist. | Sales/order owner and PM approve. |
| Payment and purchasing | Financial documents and vendor commitments affect cash flow and cost. | Prepare only and track status. | Accounting, purchasing, or PM approves. |
| Customer updates | Wrong promise or bad tone can damage trust. | Draft and summarize. | PM or sales reviews based on sensitivity. |
| Site and install readiness | Bad readiness data causes failed delivery, delays, damage, or install friction. | Request, assemble, and recommend. | PM/installer confirms release and schedule. |
| Backorder, substitution, extraction, and punch list | Scope, margin, timing, or relationship impact may require customer decision. | Detect and prepare decision options. | Sales owns customer-facing choice; PM coordinates execution. |
| Completion and relationship continuity | Missing proof can delay closeout, final invoice, commission, service, or warranty readiness. | Request, monitor, and organize proof. | PM validates; rep reviews relationship follow-up. |

## Capability Implications

This workflow supports these capability clusters:

- Approval and handoff readiness.
- Order coordination.
- Install readiness.
- Customer communication and rep visibility.
- Completion and relationship continuity.

It also supports a future `order-execution` domain or lens if the project/order pages become too dense for `projects` alone.

## Schema Implications

The post-close workflow needs explicit objects and events for:

- `ApprovalProof` and `CustomerCommitmentEvent`.
- `PurchaseOrderReview` and `ContractReviewHighlight`.
- `OrderReadinessChecklist`, `OrderReadinessState`, and `OrderBlocker`.
- `PaymentTerms`, `InvoiceMilestonePlan`, `Invoice`, and `PaymentMilestone`.
- `VendorPurchaseOrder`, `VendorAcknowledgmentEvent`, and `LeadTimeStatus`.
- `CustomerStatusUpdateEvent` and `RepVisibilityEvent`.
- `SiteSurvey`, `DeliveryReadinessState`, `ReadinessExport`, and `ReceivingEvent`.
- `InstallScheduleEvent`, `InstallationCompletionPacket`, `PunchListItem`, and `CompletionProofRequest`.
- `RelationshipFollowUpPlan` and `InstalledBaseLifecycleTrigger`.

## Validation Needs

Before this becomes implementation policy, the wiki needs more detail on:

- Order/execution readiness completeness.
- Site survey field thresholds and installer release needs.
- Payment milestone detail and accounting/purchasing procedure.
- Project status events that should notify the sales rep.
- Customer communication policy and escalation rules.
- Install completion proof standards.
- Post-install relationship-management cadence.

Do not treat current Fit Supply or NetSuite sequence as the answer key. Treat it as evidence for the coordination pattern and then design the target-state workflow around explicit state, review, provenance, and human ownership.
