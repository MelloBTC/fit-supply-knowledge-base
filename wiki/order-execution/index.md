---
title: Order Execution
type: Index
domain: order-execution
knowledge_scope: target-state
status: Draft
last_reviewed:
reviewed_by:
sources:
  - schema.md
  - PROJECT_CONTEXT.md
  - docs/session-handoff.md
  - wiki/knowledge-base/information-architecture-pressure-test.md
  - wiki/order-execution/close-won-to-delivery-workflow.md
  - wiki/order-execution/order-execution-readiness-agent-requirements.md
  - wiki/order-execution/order-execution-state-model.md
  - wiki/order-execution/order-execution-transition-gate-rules.md
related:
  - [[../index|Fit Supply Knowledge Base Index]]
  - [[../projects/index|Projects]]
  - [[../governance/index|Governance]]
  - [[../sales/freight-install-quote-readiness|Freight And Install Quote Readiness]]
  - [[../sales/proposal-package-readiness|Proposal Package Readiness]]
  - [[../governance/agent-evaluation-fixtures|Agent Evaluation Fixtures]]
  - [[../knowledge-base/domain-model-review|Domain Model Review]]
  - [[../knowledge-base/information-architecture-pressure-test|Information Architecture Pressure Test]]
agent_answerability:
  - What belongs in the Order Execution domain?
  - Which pages define order-execution workflow, readiness behavior, state, and transition gates?
  - What must be true before post-close work can safely advance to the next state?
tags:
  - domain-index
  - order-execution
  - readiness
  - workflow-state
provenance_notes: Created 2026-06-27 as the bounded order-execution pilot migration after Josh approved promoting the lane from projects/governance storage into a first-class wiki domain. This index is a navigation home, not a claim that all order-execution policy is fully validated or build-ready.
---

# Order Execution

Order Execution covers the target-state workflow after customer commitment: order readiness, vendor ordering, site readiness, delivery/install readiness, completion proof, transition gates, and relationship-ready handoff.

This domain exists because the order-execution pages created enough navigation pressure to outgrow a split between `projects` and `governance`. It is still a bounded pilot domain. Broader `v0.4` migration remains deferred.

## Current Pages

- [[close-won-to-delivery-workflow|Close Won To Delivery Workflow]] - Case-backed workflow from approval through delivery, install completion, and relationship continuity.
- [[order-execution-readiness-agent-requirements|Order Execution Readiness Agent Requirements]] - Readiness coordinator behavior, human boundaries, rep visibility, and data shape implications.
- [[order-execution-state-model|Order Execution State Model]] - Target-state ladder from quote-ready through relationship-ready.
- [[order-execution-transition-gate-rules|Order Execution Transition Gate Rules]] - Gate behavior, blockers, warnings, review boundaries, overrides, and evaluation expectations.

## Related Pages

- [[../sales/freight-install-quote-readiness|Freight And Install Quote Readiness]] remains in `sales`; its reviewed F&I assumptions feed order-execution handoff context.
- [[../sales/proposal-package-readiness|Proposal Package Readiness]] remains in `sales`; its reviewed project context, design assets, proposal delivery event, and accepted package assumptions should not be rediscovered after approval.
- [[../governance/agent-evaluation-fixtures|Agent Evaluation Fixtures]] remains in `governance`; it defines synthetic-fixture and trace discipline without moving the wiki into product implementation.
- [[../projects/index|Projects]] remains the broader delivery and project-lifecycle domain.

## Boundaries

- Do not treat this migration as a full `v0.4` restructure.
- Do not move quote-readiness, lead-intelligence, installed-base, or agent-readiness pages into new domains from this pilot alone.
- Do not treat order-execution gate rules as final dealer-approved policy; unresolved thresholds and review rules still require validation.
- Do not import upstream machine-readable fixtures or product evaluator implementation artifacts unless Josh explicitly opens that scope.

## Maintenance Notes

- Keep all order-execution state and gate pages linked through this index.
- Link back to `sales`, `projects`, `governance`, and `knowledge-base` when a page depends on quote assumptions, broader project lifecycle, evaluation discipline, or structure governance.
- Leave pages in Draft until reviewed.
