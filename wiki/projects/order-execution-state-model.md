---
title: Order Execution State Model
type: Workflow
domain: projects
knowledge_scope: target-state
status: Draft
last_reviewed:
reviewed_by:
sources:
  - raw/imports/fast-os-capability-roadmap-source-inventory.md#fscr-010
  - raw/imports/fast-os-capability-roadmap-source-inventory.md#fscr-009
  - wiki/projects/close-won-to-delivery-workflow.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/06-agent-workflow-decomposition/order-execution-state-transition-model-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/06-agent-workflow-decomposition/order-execution-transition-gate-rules-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/06-agent-workflow-decomposition/order-execution-readiness-agent-requirements-v1.md
related:
  - [[close-won-to-delivery-workflow|Close Won To Delivery Workflow]]
  - [[order-execution-readiness-agent-requirements|Order Execution Readiness Agent Requirements]]
  - [[../governance/order-execution-transition-gate-rules|Order Execution Transition Gate Rules]]
  - [[../knowledge-base/distributor-workflow-map|Distributor Workflow Map]]
  - [[../knowledge-base/domain-model-review|Domain Model Review]]
agent_answerability:
  - What are the target-state order-execution states from quote-ready through relationship-ready?
  - What evidence and review must exist before a project moves to the next state?
  - How should blockers, warnings, parallel progress, and overrides work in order execution?
tags:
  - order-execution
  - state-model
  - readiness
  - roadmap-derived
provenance_notes: Synthesized from roadmap FSCR-010. This is a target-state state model, not a claim that Fit Supply currently operates exactly this way.
---

# Order Execution State Model

This page defines the target-state state model for order execution. It exists to prevent false progress between customer approval, order handoff, vendor ordering, site readiness, delivery/install, completion, and relationship follow-up.

The model should be read with [[order-execution-readiness-agent-requirements|Order Execution Readiness Agent Requirements]] and [[../governance/order-execution-transition-gate-rules|Order Execution Transition Gate Rules]].

## Core Principle

State changes must be earned.

```text
state
-> required facts
-> blocking gaps
-> warning gaps
-> owner
-> review event
-> source evidence
-> allowed next transition
```

The durable object is reviewed workflow state. Checklists, PDFs, installer views, customer summaries, and accounting packets are outputs from reviewed state, not the source of truth.

## State Ladder

```text
quote-ready
-> approval-proof-ready
-> customer-committed / closed-won
-> order-ready
-> vendor-order-ready
-> site-ready
-> delivery-ready
-> install-scheduled
-> install-complete
-> relationship-ready
```

Some states can progress in parallel. Payment setup, site survey collection, vendor ordering, and timing review can overlap when unresolved gaps do not affect the next action.

## State Definitions

| State | Business Meaning | Primary Owner | Required Evidence | Typical Blockers |
| --- | --- | --- | --- | --- |
| `quote-ready` | Quote can be sent or presented with known scope, pricing, F&I, and customer-facing assumptions. | Sales rep | Quote version, customer/account, line items, pricing/F&I status, known warnings. | Missing required F&I, missing custom options, unapproved customer-facing estimate, unresolved quote-critical site risk. |
| `approval-proof-ready` | A candidate signed quote, customer PO, or approval artifact may prove commitment. | Sales rep / order owner | Signed quote, PO, or source message linking to accepted quote version. | Missing formal approval artifact, unclear signer, quote version mismatch. |
| `customer-committed / closed-won` | Customer commitment is confirmed, but operational readiness is not assumed. | Sales rep / order owner | Confirmed approval proof, accepted quote version, customer commitment event. | PO mismatch, non-standard contract terms, missing approval review. |
| `order-ready` | Sold scope is complete enough for internal handoff and order coordination to begin. | Project manager / order owner | Order readiness state, billing/install contacts, quote scope, site/project context, payment terms, readiness gap review. | Missing billing/payment facts, missing install address/site contact when needed, unresolved PO mismatch, unresolved contract issue. |
| `vendor-order-ready` | Vendor purchasing can proceed for reviewed quote lines. | Purchasing / project manager | Vendor split, SKUs/options, ship-to path, cost/source version, approved custom details. | Missing custom colors/options/artwork, wrong SKU, missing ship-to path, unresolved payment/vendor policy, unapproved vendor commitment. |
| `site-ready` | Site facts are complete enough for delivery/install planning at the current risk level. | Project manager | Site survey, access facts, room/site constraints, special instructions, layout requirement decision, risk review. | Missing required survey, unresolved floor anchoring/floor scan/waiver, missing access constraints where install cost or delivery success may change. |
| `delivery-ready` | Installer or delivery team can receive an executable readiness view or optional export. | Project manager / install coordinator | Delivery readiness state, equipment list, layout, site summary, extraction instructions, receiving status, completion requirements. | Equipment not received, missing/damaged items, missing extraction disposition, missing required layout, site not ready, schedule not confirmed. |
| `install-scheduled` | Installation date/window is confirmed with customer and installer. | Project manager | Install schedule event, customer-approved window, installer availability, site/equipment readiness. | Unrealistic timeline, customer not ready, installer unavailable, incomplete inventory, unresolved access risk. |
| `install-complete` | Installer has submitted completion proof and exceptions are reviewed. | Project manager | Customer signature on delivery confirmation, completion pictures, item list/notes, completion date, punch list or damage notes if any, serials if needed. | Missing signature, missing pictures, incomplete install, damage, missing item/parts, punch list, customer dispute. |
| `relationship-ready` | Project can move into account follow-up, installed-base context, service/warranty, and future expansion. | Sales rep / account owner | Completion review, installed asset context, relationship follow-up plan. | Unresolved customer issue, missing installed-base context, no owner/cadence for follow-up. |

## Transition Summary

| Transition | Gate Question | Required Review | Blocks If |
| --- | --- | --- | --- |
| `quote-ready -> approval-proof-ready` | Is there formal proof that can be reviewed? | Sales/order owner review. | No signed quote or PO, or only informal approval where policy requires formal proof. |
| `approval-proof-ready -> customer-committed / closed-won` | Does the artifact match the accepted quote and customer commitment? | Sales rep or order owner confirms. | Wrong quote version, unclear approval authority, unresolved PO mismatch, missing signed quote/PO when required. |
| `customer-committed / closed-won -> order-ready` | Is the sold scope complete enough for operations to act? | PM/order owner with sales context. | Missing approval validation, billing/payment blockers, non-standard contract terms, required order facts missing. |
| `order-ready -> vendor-order-ready` | Can vendor commitments be made safely? | Purchasing / PM approval. | Missing exact SKU/options, custom details, ship-to path, approved costs, or required payment condition. |
| `order-ready -> site-ready` | Are site facts sufficient for the current delivery/install risk? | PM/installer review for risky or uncertain facts. | Required site survey missing, floor anchoring unresolved, high-risk access unknown, special instructions missing when required. |
| `vendor-order-ready -> delivery-ready` | Is inventory complete enough to release to installer or schedule delivery? | PM/installer or receiving owner. | Missing/damaged/backordered items affect install, or receiving status is unknown. |
| `site-ready -> delivery-ready` | Can delivery/install execute without reconstructing project context? | PM/installer review. | Required layout missing, extraction disposition unknown, customer responsibilities unclear, access risk unresolved. |
| `delivery-ready -> install-scheduled` | Can the date be promised and executed? | PM, customer, and installer confirmation. | Site not ready, inventory not ready, schedule conflict, impossible timeline, unreviewed customer promise. |
| `install-scheduled -> install-complete` | Is the install complete, accepted, and documented enough for final invoice? | PM validation. | Missing pictures, missing customer signature, punch list, damage, missing items/parts, or customer refusal. |
| `install-complete -> relationship-ready` | Is the customer relationship ready for post-install follow-up? | Sales/account owner review. | Unresolved exception, missing installed-base context, no owner/cadence. |

## Blocker, Warning, And Override Model

The state model separates requirement level from severity.

| Field | Example Values | Why It Matters |
| --- | --- | --- |
| Requirement level | Always required, conditionally required, optional, edge-case only. | Determines whether the fact applies to this project. |
| Severity | Blocker, warning, informational, monitor. | Determines whether state transition is allowed. |
| Owner | Sales, PM, accounting, purchasing, installer, customer, management, specialist reviewer. | Determines who must resolve or approve. |
| Timing | Quote creation, approval, order handoff, vendor order, site readiness, delivery readiness, install closeout, relationship follow-up. | Determines when the gap matters. |
| Routing mode | Internal task, customer-facing draft, review escalation, optional export. | Determines how the coordinator moves the issue forward. |
| Review boundary | No review, owner review, manager review, accounting review, PM/installer review, explicit customer sign-off. | Determines who can clear the transition gate. |

Working rule:

```text
blocker = cannot transition until resolved or explicitly overridden
warning = can transition, but owner and downstream users must see it
informational = context preserved for later work
monitor = future check created without blocking current progress
```

Overrides should be rare and audited. An override should record who approved it, what transition was allowed, what evidence was reviewed, what risk was accepted, and what follow-up or monitor remains open.

## Parallel Progress

The state model should not freeze the whole project when a gap matters later.

| Situation | Recommended Behavior |
| --- | --- |
| Billing/payment information is missing, but site survey can proceed. | Block invoicing/order release if needed; collect site readiness facts in parallel. |
| Install address is missing, but equipment ships to installer/warehouse first. | Warn at order readiness; block direct-to-site shipment or install scheduling until resolved. |
| Custom upholstery or artwork is missing. | Allow quote follow-up with visible warning when appropriate; block affected vendor PO line until exact selection is confirmed. |
| Site survey is missing where install cost may change. | Warn before quote send; block delivery/install release until site risk is resolved. |
| Special delivery instructions are missing for a non-standard site. | Continue vendor ordering if not direct-to-site; block delivery release or install scheduling until instructions are confirmed. |
| Floor anchoring is unresolved. | Allow quote with warning when appropriate; block install release until scan, waiver, or risk acceptance is reviewed. |

This prevents two failure modes: dragging every project through an oversized checklist, and letting a loose checklist recreate the handoff problem.

## Minimum State Event Shape

This is not final implementation schema. It is the minimum event shape implied by the workflow.

| Object / Event | Purpose |
| --- | --- |
| `WorkflowState` | Current stage of a project, quote, order, site, delivery, install, or relationship workflow. |
| `StateTransitionEvent` | Records from-state, to-state, trigger, actor, timestamp, review decision, and source evidence. |
| `ReadinessGap` | Tracks a missing, uncertain, stale, mismatched, or risky fact. |
| `BlockerResolutionEvent` | Records how a blocker was resolved, by whom, and with what evidence. |
| `WarningAcknowledgementEvent` | Records that an owner saw and accepted a warning while allowing progress. |
| `ReviewEvent` | Captures human approval, rejection, correction, or override. |
| `SourceEvidenceLink` | Links each state fact to the artifact, message, file, survey, quote, PO, photo, or human confirmation that supports it. |
| `OwnerRoutingEvent` | Assigns a gap, review, or missing-information request to the right person or role. |
| `ExternalRequestEvent` | Records customer-facing or installer-facing requests generated from missing state. |
| `ReadinessExport` | Optional PDF, packet, installer view, accounting view, or customer summary generated from reviewed state. |

## Governance Relationship

This page defines the project-state lane. The gate policy lives in [[../governance/order-execution-transition-gate-rules|Order Execution Transition Gate Rules]].

As a rule of thumb:

- `projects` explains the workflow state, owner handoffs, and business meaning.
- `governance` explains blocker/warning policy, review boundaries, override records, and evaluation expectations.

Do not promote `order-execution` into a new top-level domain yet. Use this page, the readiness requirements page, and the governance gate page as the compiled evidence for whether that future move is justified.
