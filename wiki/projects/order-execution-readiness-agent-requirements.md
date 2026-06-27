---
title: Order Execution Readiness Agent Requirements
type: Workflow
domain: projects
knowledge_scope: target-state
status: Draft
last_reviewed:
reviewed_by:
sources:
  - raw/imports/fast-os-capability-roadmap-source-inventory.md#fscr-009
  - raw/imports/fast-os-capability-roadmap-source-inventory.md#fscr-010
  - wiki/projects/close-won-to-delivery-workflow.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/06-agent-workflow-decomposition/order-execution-readiness-agent-requirements-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/06-agent-workflow-decomposition/order-execution-state-transition-model-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/06-agent-workflow-decomposition/order-execution-transition-gate-rules-v1.md
related:
  - [[close-won-to-delivery-workflow|Close Won To Delivery Workflow]]
  - [[order-execution-state-model|Order Execution State Model]]
  - [[../governance/order-execution-transition-gate-rules|Order Execution Transition Gate Rules]]
  - [[../knowledge-base/agent-capability-map|Agent Capability Map]]
  - [[../knowledge-base/distributor-workflow-map|Distributor Workflow Map]]
agent_answerability:
  - What should an order-execution readiness coordinator detect, classify, route, draft, preserve, monitor, recommend, review, and record?
  - Which order-execution actions can AI prepare, and which require human review?
  - When should sales be notified versus asked to make a customer-facing decision?
tags:
  - order-execution
  - readiness
  - agent-requirements
  - roadmap-derived
provenance_notes: Synthesized from roadmap FSCR-009 and FSCR-010 as a target-state wiki pattern. The source is implementation-adjacent, so this page preserves durable workflow and governance requirements rather than treating the artifact as a final code spec.
---

# Order Execution Readiness Agent Requirements

This page defines the target-state behavior expected from an order-execution readiness coordinator.

The key product boundary is simple: the system should help make the next state true. It should not act like an autonomous ordering agent, and it should not treat a status change as proof that the project is ready.

## Business Outcome

Prevent false progress after customer approval while helping sales, project management, purchasing, accounting, installers, customers, and managers resolve the right missing facts at the right time.

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

The readiness coordinator exists because these states are different:

- Closed-won does not mean operationally ready.
- Delivery-ready does not mean install-complete.
- Install-complete does not mean relationship-ready.

## Coordinator Posture

The readiness coordinator should prepare, route, monitor, and record. Humans still own commitment, financial, customer-promise, vendor, install-release, completion, and exception decisions.

| Behavior | Target-State Requirement | Human Boundary |
| --- | --- | --- |
| Detect | Identify missing, mismatched, stale, uncertain, or risky readiness facts from quotes, POs, contracts, email, layouts, site/access evidence, vendor tracking, installer confirmations, delivery confirmations, photos, and human updates. | Humans review uncertain extraction and high-risk findings. |
| Classify | Evaluate each gap against the active transition gate as blocker, warning, informational, or monitor. | Humans can correct severity and requirement applicability. |
| Route | Assign each gap to the role that can resolve it: sales, PM, accounting, purchasing, installer, customer, management, or specialist reviewer. | The human owner remains accountable for resolution. |
| Draft | Prepare customer requests, internal tasks, installer questions, PM summaries, review briefs, and customer update drafts. | Customer-facing messages require review unless a future policy proves otherwise. |
| Preserve | Link each readiness fact to source evidence, confidence, timestamp, actor, and related workflow state. | Humans can mark evidence insufficient or attach corrected proof. |
| Monitor | Watch unresolved blockers, warning carry-forward, stale quotes, delayed deposits, backorders, missing receiving confirmation, missing completion proof, and unresolved exceptions. | Humans decide escalation tone, customer promise, substitution, concession, cancellation, or recovery path. |
| Recommend | Suggest the next safe action and explain which transition it unlocks. | Humans approve trust-sensitive, financial, or customer-facing action. |
| Request review | Ask the relevant owner to approve, hold, override, or request more information. | Required for approval proof, PO mismatch, contract terms, vendor commitment, install release, schedule promise, completion, and exception closure. |
| Record | Write state transition events, review events, blocker resolutions, warning acknowledgements, override decisions, customer requests, and rep visibility events. | The audit trail should preserve who decided what and why. |

## Human Review Hard Stops

The coordinator must not autonomously approve:

- Customer commitment or closed-won conversion.
- PO mismatch or non-standard contract term acceptance.
- Vendor commitments, customer-facing lead-time promises, or schedule promises.
- Required payment overrides or commercial concessions.
- Install release, delivery exception acceptance, or early-delivery risk.
- Clean install completion when proof or exceptions are unresolved.
- Relationship-ready state when customer issues, installed-base truth, or substitution records remain wrong.

These are not generic caution areas. They are the trust, money, vendor, site, and customer-experience boundaries where false automation would create business risk.

## Rep Visibility

Sales owns the customer relationship, but sales should not be pulled into every operational detail.

The readiness coordinator should separate:

```text
visibility = keep the rep aware
decision needed = ask the rep to act
customer-sensitive = rep and PM decide who communicates
```

| Situation | Default Treatment |
| --- | --- |
| Customer commitment confirmed, order-ready review passes or is held, delivery/install schedule is confirmed, completion proof is received, or the project becomes relationship-ready. | Notify sales because relationship state changed. |
| Deposit delay, backorder, substitution, install exception, damage, missing parts, customer dispute, or punch list affects customer promise, commercial outcome, or trust. | Route to sales for decision or co-decision. |
| Installer receiving confirmation, routine site survey review, missing packing slip, or credible backorder ETA with no customer-promise impact. | PM-led; sales is visible only when timing, scope, or relationship trust is affected. |

Working rule:

```text
Notify sales when relationship state changes.
Ask sales to act when the customer promise, commercial outcome, or trust relationship changes.
```

## State-To-Agent Summary

| State / Gate | Coordinator Should Do | Must Not Do Without Review |
| --- | --- | --- |
| Quote creation / quote release | Warn when site/access evidence is recommended for dealer-coordinated delivery or extraction of large/access-sensitive equipment; carry unresolved site/access warnings forward when quote is sent anyway. | Block quote release solely because site/access evidence is missing, or leave an unresolved warning unassigned. |
| `quote-ready -> approval-proof-ready` | Detect approval signal, request formal signed quote or PO when required, and link approval to quote version. | Treat customer enthusiasm as approval proof. |
| `approval-proof-ready -> closed-won` | Prepare approval review, compare PO or signed quote to accepted quote, and highlight signer/version uncertainty. | Mark closed-won without human confirmation. |
| `closed-won -> order-ready` | Evaluate order readiness, route billing/payment/contact/contract/layout/site/custom/F&I gaps, and preserve warnings that can move in parallel. | Release operational handoff when unresolved blockers affect the next action. |
| `order-ready -> vendor-order-ready` | Check SKU, quantity, vendor split, options, ship-to path, cost freshness, custom details, and payment condition; block affected lines when line-specific details are missing. | Create or approve vendor commitments before required payment, source-backed custom choices, and human owner confirmation exist. |
| `order-ready -> site-ready` | Extract site/access facts from available evidence, keep default customer prompts simple, and route high-risk or stale facts to PM/installer review. | Require unnecessary proof for normal orders after source-backed confirmation, or clear high-risk site facts without review. |
| `vendor-order-ready + site-ready -> delivery-ready` | Assemble installer-facing readiness view, confirm receiving evidence, classify backorder/substitution risk, and ensure layout, extraction, and completion requirements are attached. | Release installer packet when PM review is missing or external execution scope is wrong. |
| `delivery-ready -> install-scheduled` | Compare readiness state to proposed schedule and draft scheduling requests. | Promise install dates autonomously. |
| `install-scheduled -> install-complete` | Request, ingest, and organize completion photos and signed delivery confirmation; create exception state for damage, missing parts, punch list, or dispute. | Mark clean complete without required proof. |
| `install-complete -> relationship-ready` | Prepare completion summary, installed-base context, unresolved issue summary, and relationship follow-up prompt. | Hide unresolved execution issues behind relationship-ready status. |

## Data Shape Implications

This is not a final schema, but the wiki should preserve the data objects implied by the workflow:

| Object / Event | Why It Matters |
| --- | --- |
| `WorkflowState` | Stores current state and next allowed transitions. |
| `TransitionGateEvaluation` | Records pass, warn, or block outcome for the active transition. |
| `ReadinessGap` | Tracks missing, mismatched, stale, uncertain, or risky facts. |
| `SourceEvidenceLink` | Preserves the artifact, message, file, survey, quote, PO, photo, or human confirmation behind a readiness fact. |
| `ReviewEvent` and `OverrideDecision` | Capture human approval, hold, correction, rejection, and accepted-risk decisions. |
| `OwnerRoutingEvent` | Routes gaps to sales, PM, accounting, purchasing, installer, customer, management, or specialist reviewer. |
| `CustomerRequestDraft` | Converts missing customer-owned facts into reviewable outreach. |
| `DeliveryTimingIntent` | Preserves ASAP, target window, hard deadline, not-before date, or unknown timing intent. |
| `SiteAccessEvidence` | Stores delivery-path and room-readiness facts with source, confidence, date, freshness, and review state. |
| `InstallerReadinessView` | Produces the reviewed external execution view from readiness state. |
| `InstalledAssetRecord` | Protects the truth of what was actually installed, especially after substitution. |
| `RepVisibilityEvent` | Keeps the sales rep aware without making sales the default owner of operational tasks. |
| `InstallationCompletionPacket` | Captures signed delivery confirmation, photos, exceptions, serials, and closeout notes. |
| `RelationshipReadinessSummary` | Connects completion to follow-up, installed-base context, and future account lifecycle. |

## Interface Pattern

The surface should be a transition-gate workspace, not a generic checklist.

Required view:

```text
Current state
Next state
Gate result
Blockers
Warnings
Owner
Evidence
Recommended action
Review controls
Rep visibility
```

Required controls include approve transition, hold transition, request info, override with reason, carry warning forward, notify sales, escalate to sales decision, and generate export from reviewed state.

## Test And Evaluation Boundary

The near-term product step implied by the roadmap source is schema-shaped test data and gate-evaluation behavior, not full autonomy.

Useful fixture shapes include clean signed-quote order, PO mismatch order, non-standard contract terms, custom-option order, site-risk order, direct-to-site versus installer-warehouse fulfillment, delayed deposit, far-future install timing, backorder substitution, completion-proof delay, damage/missing-parts exception, relationship-ready clean closeout, and related flooring/extraction dependency.

These fixtures should not be copied from raw customer files. They should test distinct gate behavior, owner boundary, evidence type, dealer policy, or review rule.

## Validation Needs

Before this becomes implementation policy, the wiki needs clearer review decisions for:

- Final rep visibility policy.
- PO and non-standard contract mismatch handling.
- Site/access capture requirements by equipment and delivery responsibility.
- Delivery timing intent, lead-time confidence, storage-risk workflow, and customer communication eligibility.
- Required record revisions after accepted substitution.
- Completion proof standards and installed-base truth after substitutions.

Keep commercial equipment catalog, product compatibility, price freshness, and model-specific answerability upstream in `fast-os-knowledge-base` until mature outputs are available to evaluate locally.
