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
  - wiki/sales/lead-to-closed-won-workflow.md
  - wiki/projects/close-won-to-delivery-workflow.md
related:
  - [[roadmap-import-plan|Roadmap Import Plan]]
  - [[agent-answerability-targets|Agent Answerability Targets]]
  - [[distributor-workflow-map|Distributor Workflow Map]]
  - [[agent-capability-map|Agent Capability Map]]
  - [[../company/commercial-fitness-distributor-operating-model|Commercial Fitness Distributor Operating Model]]
  - [[../sales/lead-to-closed-won-workflow|Lead To Closed Won Workflow]]
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
provenance_notes: Domain review checkpoint based on the first roadmap synthesis pass and source inventory. This page records wiki structure decisions, not current Fit Supply operating facts.
---

# Domain Model Review

This page records the first domain model review after the initial roadmap synthesis pass.

The review question is whether the starter wiki domains should expand before more roadmap artifacts are synthesized. The short answer is: keep the top-level domain model stable for now, but treat `order-execution` as the next active workflow lens.

## Decision Summary

Do not add new top-level wiki domains yet.

The current schema is still structurally correct for the first synthesis pass: `sales`, `design`, `equipment`, `projects`, `service`, `company`, `governance`, and `knowledge-base` remain usable homes. Adding new folders now would create structure before there is enough compiled page density to justify the maintenance cost.

The strongest domain-expansion signal is `order-execution`. The first compiled pages now live under `projects` and `governance` with clear `order-execution` tags and links. Reassess a dedicated `wiki/order-execution/` domain only after the new pages create enough repeated navigation, ownership, or state-boundary explanation to justify the maintenance cost.

## Candidate Decisions

| Candidate | Current Decision | Home For Now | Evidence | Promotion Trigger |
| --- | --- | --- | --- | --- |
| `order-execution` | Active synthesis lane, but not a top-level domain yet. | `wiki/projects/` for order-readiness and execution workflow pages; `wiki/governance/` for gate rules, human review boundaries, and evaluation patterns. | FSCR-008 shows closed-won, order-ready, delivery-ready, install-complete, and relationship-ready as distinct states. FSCR-009 and FSCR-010 are now synthesized into readiness, state-model, and gate-rule pages. FSCR-011 remains the evaluation-fixture follow-on. | Create `wiki/order-execution/` only if the new pages make `projects` and `governance` navigation too broad or force repeated cross-domain explanations. |
| `operating-model` | Keep as a canonical lens, not a new domain. | `wiki/company/commercial-fitness-distributor-operating-model.md`, linked from root and workflow pages. | FSCR-002 and FSCR-003 establish the parent lifecycle and data-object spine, but the current page works as the parent map without a new folder. | Promote only if separate lifecycle, role, value-stream, and data-object pages become hard to maintain inside `company` and `knowledge-base`. |
| `agent-workflows` | Keep as a knowledge-base answerability lens. | `wiki/knowledge-base/agent-capability-map.md` and future knowledge-base pages about agent navigation, boundaries, and build bridges. | FSCR-006 identifies capability clusters across domains, but these are not final product agents and should not be named as a product surface too early. | Promote only after multiple compiled pages need a shared home for agent workflow contracts rather than domain workflow content. |
| `lead-intelligence` or `prospecting` | Defer as a sales sub-lane. | `wiki/sales/` when target-state sales pages are mature enough. | FSCR-012 is useful but includes provisional hunter-sales validation labels, so promoting it now would risk turning tentative policy into structure. | Reassess after lead qualification, source intelligence, and hunter-sales patterns have validated compiled pages. |
| `installed-base` | Defer as a lifecycle lens across service, equipment, and sales. | `wiki/service/`, `wiki/equipment/`, and relationship-continuity sections until sourced service/warranty pages exist. | The operating model says installed assets matter, but the current compiled evidence is strategic rather than enough for durable rules. | Reassess after service, warranty, parts, replacement, or post-install relationship pages are sourced. |

## Current Order-Execution Lane

The order-execution lane now has three compiled pages without changing the top-level schema:

- [[../projects/order-execution-readiness-agent-requirements|Order Execution Readiness Agent Requirements]].
- [[../projects/order-execution-state-model|Order Execution State Model]].
- [[../governance/order-execution-transition-gate-rules|Order Execution Transition Gate Rules]].

These pages preserve the domain split:

- `projects` explains workflow state, readiness behavior, owners, and handoffs.
- `governance` explains blocker/warning policy, review boundaries, overrides, and evaluation expectations.

## Next Review Decision

The next coherent slice should choose between two options:

1. Review FSCR-011 if the next priority is evaluation discipline for order-execution gates.
2. Reassess the domain model if the new pages already create enough navigation pressure to justify a top-level `order-execution` domain.

The current recommendation is to keep the top-level domain model stable through at least one follow-on review.

## Boundaries

- Keep commercial equipment catalog/schema, equipment answerability, source manifest pattern, validation gates, and repo-boundary option work upstream in `fast-os-knowledge-base` until mature outputs are available to evaluate.
- Do not bulk-import roadmap artifacts.
- Do not promote provisional hunter-sales scenarios into durable target-state rules without preserving validation labels.
- Do not turn current Fit Supply or NetSuite evidence into the target-state answer key.

## Working Rule

Use the smallest structure that preserves meaning.

For the next pass, that means a named `order-execution` lens inside existing domains, not a new top-level domain. If the next order-execution pages repeat the same navigation, ownership, and state-boundary explanations, that repetition is the evidence needed to promote the lens into a first-class domain.