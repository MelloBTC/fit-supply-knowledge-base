---
title: Order Execution Transition Gate Rules
type: Governance
domain: order-execution
knowledge_scope: target-state
status: Draft
last_reviewed:
reviewed_by:
sources:
  - raw/imports/fast-os-capability-roadmap-source-inventory.md#fscr-010
  - raw/imports/fast-os-capability-roadmap-source-inventory.md#fscr-009
  - wiki/order-execution/order-execution-state-model.md
  - wiki/order-execution/order-execution-readiness-agent-requirements.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/06-agent-workflow-decomposition/order-execution-transition-gate-rules-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/06-agent-workflow-decomposition/order-execution-state-transition-model-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/06-agent-workflow-decomposition/order-execution-readiness-agent-requirements-v1.md
related:
  - [[order-execution-state-model|Order Execution State Model]]
  - [[order-execution-readiness-agent-requirements|Order Execution Readiness Agent Requirements]]
  - [[close-won-to-delivery-workflow|Close Won To Delivery Workflow]]
  - [[../governance/source-manifest|Source Manifest]]
  - [[../governance/agent-evaluation-fixtures|Agent Evaluation Fixtures]]
  - [[../knowledge-base/domain-model-review|Domain Model Review]]
agent_answerability:
  - Which facts should block, warn, monitor, or inform an order-execution state transition?
  - Which order-execution decisions require human review or override records?
  - How should gate rules preserve evidence, owner routing, safe parallel progress, and rep visibility?
tags:
  - order-execution
  - transition-gates
  - human-review
  - governance
  - roadmap-derived
provenance_notes: Synthesized from roadmap FSCR-010 with FSCR-009 support. Exact thresholds are likely dealer-specific, so this page records durable gate behavior and review policy rather than a final operational ruleset.
---

# Order Execution Transition Gate Rules

This governance page defines how target-state order-execution transitions should be evaluated.

The central rule is:

```text
Block the state transition only when the missing or risky fact affects the next action.
```

That rule prevents two opposite failures:

- Moving forward when the next action is unsafe.
- Freezing the whole project because of a fact that matters later, not now.

## Terms

| Term | Meaning |
| --- | --- |
| Blocker | Prevents the transition until resolved or explicitly overridden. |
| Warning | Allows the transition, but stays visible to the owner and downstream users. |
| Informational | Preserves context for later use without affecting the transition. |
| Monitor | Creates a future check without blocking the current transition. |

## Gate Behavior Standard

Order-execution gate rules should consistently:

- Evaluate the active gate before deciding blocker versus warning.
- Block only the next unsafe action while safe parallel work continues.
- Classify fulfillment-path-dependent gaps only after ship-to path is known.
- Make blockers line-specific when possible.
- Preserve source evidence or human confirmation for every readiness fact.
- Keep human review hard for commitment, vendor order, customer promise, install release, completion, and exception closure.
- Keep delivery timing promises separate from internal lead-time planning.
- Route far-future timing and storage-risk decisions to PM review before manufacturer order release.

## Gate Summary

| Gate | Business Question | Default Rule |
| --- | --- | --- |
| `quote-ready -> approval-proof-ready` | Has the customer produced a reviewable commitment signal? | Do not treat customer enthusiasm as approval proof. Preserve the signal, then request or route formal proof. |
| `approval-proof-ready -> customer-committed / closed-won` | Does the approval proof establish a valid customer commitment? | Closed-won means commitment is confirmed. It does not mean the project is operationally ready. |
| `customer-committed / closed-won -> order-ready` | Is the sold scope complete enough for internal handoff and order coordination to begin? | Order-ready requires enough reviewed scope for coordination. It does not require every delivery/install fact if safe parallel work can continue. |
| `order-ready -> vendor-order-ready` | Can the dealer safely make vendor commitments for reviewed order lines? | Vendor-order-ready is line-specific when possible. Block affected lines without freezing unrelated reviewed lines unless the project must move as one package. |
| `order-ready -> site-ready` | Are site facts complete enough for the current project risk level? | Site-ready means known site risk is reviewed for this project. It does not mean every site has the same required fields. |
| `vendor-order-ready + site-ready -> delivery-ready` | Can the installer or delivery team receive an executable readiness view? | Delivery-ready means external execution can proceed without reconstructing the project from scattered artifacts. |
| `delivery-ready -> install-scheduled` | Can the dealer safely promise and coordinate an installation date? | Install-scheduled is a customer promise. The system may recommend windows, but humans confirm timing until scheduling policy is proven. |
| `install-scheduled -> install-complete` | Is the installation complete, accepted, and documented? | Install-complete requires proof, not just a scheduled install date passing. |
| `install-complete -> relationship-ready` | Can the project move from execution closeout into account relationship management? | Relationship-ready means follow-up can happen from a position of confidence; unresolved execution issues remain visible. |

## Human Review Boundaries

The gate policy should require human review for:

- Approval proof, signer authority, and quote-version match.
- PO mismatch, commercial/legal terms, and non-standard contract language.
- Payment condition override, vendor PO release, and customer-facing timing promise.
- Package-splitting decisions when custom or blocked lines affect freight, receiving, install readiness, package price, or customer promise.
- Site/access risk review when customer confirmation is missing, vague, contradicted, stale, or high risk.
- Early delivery into incomplete construction or renovation rooms.
- Backorder decisions that affect customer promise, substitution, concession, cancellation, scope, margin, or trust.
- Install schedule promise.
- Clean completion, damage/missing-parts exception closure, and customer dispute handling.
- Relationship-ready state when installed-base truth, substitution records, or unresolved customer issues remain open.

Overrides should be rare and explicit. An override must record actor, state transition, reviewed evidence, accepted risk, reason, and follow-up or monitor.

## Evidence And Owner Routing

A gate evaluation should not only say pass or fail. It should identify:

- The readiness fact or gap.
- Its requirement level and severity.
- The owner who can resolve or approve it.
- The source evidence needed to clear it.
- The review boundary.
- The customer-facing, installer-facing, or internal task it should become.
- The downstream state the action unlocks.

The coordinator should preserve evidence rather than flattening it into a checkbox. Source evidence can include quote versions, signed quote, PO, contract, customer email, site survey, rep note, voice note, photo, video, vendor tracking, installer confirmation, delivery confirmation, completion photos, human review decision, or structured customer confirmation.

## Parallel Progress Policy

The gate system should allow parallel work when risk allows it.

Examples:

| Gap | Block Now? | Carry Forward? |
| --- | --- | --- |
| Billing information missing while site survey can proceed. | Block invoicing/order release if required. | Continue site readiness collection. |
| Install address missing while ship-to path is installer warehouse. | Block direct-to-site shipment or install scheduling. | Warn at order readiness. |
| Custom upholstery missing. | Block affected vendor PO line. | Allow unrelated reviewed lines only after PM/purchasing package-splitting review. |
| Site survey missing where install cost may change. | Warn before quote send. | Block delivery/install release until site risk is resolved. |
| Special delivery instructions missing for non-standard site. | Block delivery release or install scheduling. | Continue vendor ordering if not direct-to-site. |
| Floor anchoring unresolved. | Block install release. | Allow earlier quote/order progress with warning when appropriate. |

## Site And Delivery Guardrails

The gate rules distinguish delivery-path readiness from room readiness.

```text
delivery-path readiness
= truck / unloading point -> entrance -> route -> vertical movement -> room entrance -> final placement path

room readiness
= destination condition: flooring, power, active construction/trades, room clearance,
customer / GC readiness, and other install dependencies
```

For normal orders, source-backed customer confirmation can clear delivery-path readiness and room readiness for v1. The system should not demand photos, videos, or segment-by-segment proof by default.

PM or installer review is required when confirmation is missing, vague, contradicted, stale, or tied to high-risk access or room conditions. Construction and renovation projects need fresher room-ready confirmation near release when doubt exists.

Customer pressure to deliver early is not room-ready evidence. If a customer requests delivery before the room is ready, the system should create a reviewed exception path and preserve customer risk acknowledgement.

## Backorder And Substitution Guardrails

Backorder escalation should be based on customer promise and required decision, not a hard day-count threshold.

PM or purchasing can monitor a backorder when it is only a lead-time fact with credible ETA, no promised date at risk, no customer choice needed, and no scope/value/margin/trust change.

Sales visibility starts when the timing buffer is shrinking, ETA confidence is weakening, a requested install window may be threatened, or customer expectation may be affected. Sales action is required when the system needs customer-facing bad-news communication, wait/partial/split/substitute/cancel/alternate-vendor decision, changed promise, product/scope/value change, concession, no credible ETA with customer expectation at risk, or trust-sensitive recovery path.

Accepted substitutions should be represented in the execution record:

- Customer-facing confirmation is preserved as structured evidence.
- Sales Order revision, amendment, link, or reviewed no-change decision is recorded.
- Vendor PO revision, reissue, replacement, or vendor-confirmed change order is reviewed when the vendor path changes.
- Layout or installer readiness view is revised or reviewed no-change when physical execution changes.
- Installed asset or service record reflects the actual installed substitute after completion.

## Completion And Relationship Guardrails

Clean install-complete requires proof. For the current Fit Supply-informed source, clean completion requires customer signature on delivery confirmation plus pictures.

Missing proof should create a completion-proof request/monitor loop. It is not the same as a damage exception unless the evidence later shows damage, incomplete work, punch list, missing parts, or customer dispute.

Relationship-ready should remain blocked when unresolved exception, punch list, damage, missing parts, customer dispute, or missing clean-completion review exists. Missing installed-base detail or follow-up cadence may be a warning unless policy makes it a blocker. If a substitute was installed but the installed-base record still shows the original item, relationship-ready should block until corrected or explicitly reviewed.

## Evaluation Expectations

Future implementation should be testable against:

- Gate classification accuracy.
- Owner routing accuracy.
- Sales visibility versus sales action routing.
- Evidence preservation.
- Human review refusal for hard-boundary decisions.
- Parallel progress without unsafe transitions.
- Customer request quality.
- Exception handling.
- Fulfillment-path-dependent classification.
- Line-specific blocking.
- Completion proof versus exception separation.
- Installed-base truth after substitution.

Minimum trace data should include input sources, extracted facts and confidence, active gate, blocker/warning decision, owner assignment, draft or recommendation, human review result, transition or hold reason, rep visibility event, and override reason. The broader synthetic-fixture and trace discipline is compiled in [[../governance/agent-evaluation-fixtures|Agent Evaluation Fixtures]].

## Open Validation Needs

Exact thresholds and dealer policy still need validation for:

- Formal approval artifacts and acceptable exceptions.
- PO/contract mismatch categories.
- Site/access evidence requirements by equipment category and delivery responsibility.
- Payment delay, parked-order, abandoned-order, and cancellation review.
- Qualified historical lead-time ranges and customer communication eligibility.
- Warehouse/storage fee handling.
- Vendor PO revision procedures after substitution.
- Completion proof exceptions and service/warranty installed-base requirements.
