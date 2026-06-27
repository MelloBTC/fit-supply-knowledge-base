---
title: Agent Evaluation Fixtures
type: Governance
domain: governance
knowledge_scope: target-state
status: Draft
last_reviewed:
reviewed_by:
sources:
  - raw/imports/fast-os-capability-roadmap-source-inventory.md#fscr-011
  - wiki/order-execution/order-execution-readiness-agent-requirements.md
  - wiki/order-execution/order-execution-state-model.md
  - wiki/order-execution/order-execution-transition-gate-rules.md
  - wiki/knowledge-base/wiki-to-agent-build-bridge.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/06-agent-workflow-decomposition/order-execution-gate-evaluation-checklist-and-eval-spec-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/06-agent-workflow-decomposition/order-execution-gate-evaluation-synthetic-test-suite-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/fixtures/order-execution-gate-evaluation-v1/README.md
related:
  - [[../order-execution/order-execution-transition-gate-rules|Order Execution Transition Gate Rules]]
  - [[../order-execution/order-execution-readiness-agent-requirements|Order Execution Readiness Agent Requirements]]
  - [[../order-execution/order-execution-state-model|Order Execution State Model]]
  - [[../order-execution/close-won-to-delivery-workflow|Close Won To Delivery Workflow]]
  - [[../knowledge-base/wiki-to-agent-build-bridge|Wiki To Agent Build Bridge]]
  - [[../knowledge-base/agent-answerability-targets|Agent Answerability Targets]]
  - [[../knowledge-base/information-architecture-pressure-test|Information Architecture Pressure Test]]
agent_answerability:
  - How should future readiness agents be tested before real customer data is loaded?
  - What should synthetic fixtures prove about gate behavior, owner routing, review boundaries, and traceability?
  - What belongs in this wiki versus a future product-side evaluator or machine-readable fixture bundle?
tags:
  - agent-evaluation
  - synthetic-fixtures
  - order-execution
  - governance
  - roadmap-derived
provenance_notes: Synthesized from FSCR-011 as governance and answerability discipline. The upstream source includes product-side fixture files and a runner; this page records the durable wiki pattern without importing machine-readable fixtures or opening product implementation scope.
---

# Agent Evaluation Fixtures

This page defines how the wiki should think about synthetic evaluation fixtures for future agent-supported workflows.

The first concrete source family is the order-execution gate evaluation suite. Its local value is not that this repo should run product tests now. Its value is that future agent behavior should be testable before real customer data, customer files, pricing, quote records, POs, photos, or private project artifacts are loaded.

## Governance Purpose

An agent-ready workflow page is not mature just because it describes a process. It should eventually be testable against the decisions that create business risk.

For order execution, the risk is false progress:

- Treating closed-won as operationally ready.
- Treating order-ready as vendor-order-ready or site-ready.
- Treating delivery-ready as install-complete.
- Treating install-complete as relationship-ready.
- Freezing the entire project when only one line, future fact, or downstream action is unsafe.
- Routing every operational issue to sales.
- Hiding customer-promise, commercial, trust, or relationship-sensitive changes from sales.
- Letting AI approve commitment, vendor, payment, customer-promise, install-release, completion, exception, or relationship-ready decisions without human review.

Evaluation fixtures make those risks explicit. They give a future evaluator a safe answer key before production behavior exists.

## Evaluation Spine

Every readiness evaluation should preserve this sequence:

```text
active gate
-> workflow state
-> source evidence or human confirmation
-> policy parameters
-> readiness gaps
-> blocker, warning, informational, monitor, or hold-for-review result
-> owner routing
-> rep visibility versus sales action
-> safe parallel progress
-> human review or override boundary
-> recorded trace event
```

The central rule is the same as the order-execution gate rules:

```text
evaluate the active gate first
block only the next unsafe action
carry forward visible warnings when later gates need them
```

## What Fixtures Must Prove

Synthetic fixtures should test behavior, not mirror private records.

| Evaluation Area | What A Passing Fixture Proves |
| --- | --- |
| Active gate classification | A fact is classified against the current transition, not treated as a global blocker or global pass. |
| Blocker, warning, monitor, hold | The evaluator distinguishes unsafe next action, safe carry-forward, future check, and review-needed uncertainty. |
| Owner routing | The gap routes to the role that can resolve it: sales, PM, accounting, purchasing, installer, customer, management, or specialist reviewer. |
| Rep visibility | Sales visibility is separate from sales action. Sales sees relationship-sensitive risk and acts only when customer-facing judgment, communication, expectation repair, or commercial path confirmation is needed. |
| Evidence preservation | Important facts link to source evidence, confidence, actor, or human confirmation. |
| Human review boundary | AI does not autonomously approve commitment, PO mismatch, contract terms, vendor order, payment override, customer promise, install release, completion, exception closure, or relationship-ready-with-issues. |
| Safe parallel progress | Non-dependent work can continue while the unsafe transition, line, or external action stays blocked. |
| Fulfillment-path logic | Direct-to-site, installer warehouse, receiving status, and site/contact gaps change severity only when that path matters. |
| Line-specific blocking | A custom option, vendor line, or package-specific blocker does not freeze unrelated reviewed work unless package policy requires it. |
| Completion proof | Missing proof creates request or monitor work; actual damage, missing parts, punch list, incomplete work, or dispute creates exception handling. |
| Relationship-ready transition | Follow-up starts only after reviewed clean closeout or explicit accepted-risk handling of unresolved issues. |

## Current Order-Execution Coverage

FSCR-011 defines the first source-backed fixture family for this repo's order-execution lane. The upstream fixture bundle covers these test shapes:

| Test Focus | What It Protects |
| --- | --- |
| Clean signed-quote order | Signed approval can support commitment after review, but does not prove every execution fact is ready. |
| PO mismatch order | PO presence is not enough when amount, scope, ship-to, bill-to, payment, tax, F&I, or accepted quote version does not match. |
| Non-standard contract terms | Detection hold is different from final blocker, warning, accepted term, correction, or rejected approval artifact. |
| Custom-option order | Missing custom detail blocks the affected vendor line and preserves the evidence requirement. |
| Site-risk order | Site/access evidence is conditional; it blocks only when project risk makes it material. |
| Fulfillment-path differences | Missing site or delivery facts can warn in one fulfillment path and block in another. |
| Delayed deposit order | Required payment blocks vendor commitment while safe site, custom, and delivery-info work may continue. |
| Backorder substitution order | Sales action depends on customer promise, decision, scope, margin, schedule, or trust impact, not a simple day count. |
| Completion-proof delay | Missing proof blocks clean install-complete without becoming damage or exception evidence by itself. |
| Damage or missing-parts exception | Exception evidence keeps the project open and visible. |
| Relationship-ready clean closeout | Relationship-ready is earned from reviewed completion and installed-base/follow-up context. |
| Related flooring or extraction dependency | A site dependency can warn early and block external execution later. |
| Far-future install timing and warehouse-fee risk | Timing and storage risk require PM review and should not become automatic fee or lead-time promises. |

The upstream bundle contains machine-readable fixture files, shared policy parameters, an expected-output schema, trace expectations, and a local runner. Those files remain in `fast-os-capability-roadmap` unless a future approved build lane intentionally imports or adapts them.

## Policy Parameters

Evaluation fixtures should keep dealer-specific or provisional thresholds explicit. For the current order-execution source family, the important parameter families are:

| Parameter | Evaluation Role |
| --- | --- |
| OQ-015 | Rep visibility and sales-action thresholds. |
| OQ-023 | PO and contract mismatch categories, owner routing, safe parallel progress, and review output. |
| OQ-024 | Site/access evidence threshold behavior. |
| OQ-025 | Delayed deposit blocker behavior, follow-up ladder, and parked-order review. |
| OQ-026 | Accepted substitution revision paths and installed-base truth before relationship-ready. |
| OQ-027 | Backorder sales-action threshold based on customer promise or required decision. |
| OQ-028 | Custom-option proof paths and package-splitting review. |
| OQ-029 | Delivery timing intent, lead-time confidence, manufacturer-order release review, and warehouse-fee workflow risk. |

The wiki can name these policy areas and explain why they matter. It should not hardcode them as universal product behavior.

## Trace Expectations

A future evaluator should leave enough trace for a human to understand why it passed, warned, blocked, held for review, or allowed parallel work.

Minimum trace shape:

| Trace Field | Why It Matters |
| --- | --- |
| Fixture or project id | Lets the evaluation be repeated and audited. |
| Active gate and from/to states | Prevents global checklist behavior. |
| Source evidence used | Prevents unsupported state changes. |
| Policy parameters used | Keeps dealer-specific thresholds configurable and reviewable. |
| Extracted facts and confidence | Shows what the evaluator believed and how strongly. |
| Gap classification | Records blocker, warning, informational, monitor, or hold-for-review. |
| Owner assignment | Shows who can resolve or approve the gap. |
| Recommended action | Distinguishes request, review, monitor, warning carry-forward, notification, escalation, and export. |
| Rep visibility decision | Separates visibility from sales action. |
| Safe parallel actions allowed | Keeps useful work moving without hiding risk. |
| Human review result | Preserves decision authority. |
| Override reason | Records accepted risk when a human allows progress anyway. |
| Transition, hold, warning, monitor, or exception event | Produces durable workflow memory. |

## Local Boundary

This page is a wiki governance page, not a product test harness.

The wiki may:

- Explain evaluation discipline.
- Link evaluation expectations to source-backed workflow and gate pages.
- Name fixture families and policy-parameter areas.
- Preserve human review, trace, and evidence requirements.
- Say when a workflow page is useful but not build-ready.

The wiki should not:

- Copy private customer, quote, PO, pricing, signature, email, photo, or NetSuite artifacts into Git.
- Import machine-readable fixture files unless a future approved build lane requires it.
- Create final product schema, migrations, API contracts, runner architecture, or evaluator implementation.
- Treat synthetic fixture answer keys as dealer-approved operating policy.
- Use evaluation fixtures to name a fully autonomous order agent.

## When To Use This Page

Use this page before moving any workflow toward build-facing requirements. It is especially relevant when a page claims that AI can classify, route, recommend, monitor, draft, or evaluate a transition.

For now, this page supports the promoted order-execution domain while staying in governance:

- `order-execution` owns post-close workflow state, readiness behavior, and lane-specific transition gate rules.
- `governance` owns fixture discipline, human review boundaries, override expectations, trace expectations, and cross-workflow evaluation patterns.
- `knowledge-base` owns the bridge from mature wiki knowledge to future build-facing requirements.

Do not create an `agent-workflows` or `agent-readiness` folder from this page alone. Reassess only when repeated navigation, ownership, or page-density pressure makes the current homes hard to maintain.
