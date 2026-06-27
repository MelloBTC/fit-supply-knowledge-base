---
title: Projects
type: Index
domain: projects
knowledge_scope: target-state
status: Draft
last_reviewed:
reviewed_by:
sources:
  - schema.md
  - PROJECT_CONTEXT.md
  - raw/imports/fast-os-capability-roadmap-source-inventory.md
  - wiki/order-execution/index.md
  - wiki/sales/freight-install-quote-readiness.md
  - wiki/sales/proposal-package-readiness.md
related:
  - [[../index|Fit Supply Knowledge Base Index]]
  - [[../order-execution/index|Order Execution]]
  - [[../governance/index|Governance]]
  - [[../knowledge-base/domain-model-review|Domain Model Review]]
  - [[../sales/freight-install-quote-readiness|Freight And Install Quote Readiness]]
  - [[../sales/proposal-package-readiness|Proposal Package Readiness]]
agent_answerability:
  - What belongs in the Projects domain?
  - Which project-lifecycle pages still belong outside the Order Execution domain?
tags:
  - domain-index
  - projects
provenance_notes: Starter domain index created during target-state skeleton setup; updated 2026-06-27 after the bounded order-execution pilot migration moved post-close readiness, state, and gate pages into wiki/order-execution/ and proposal package readiness was linked as a sales-stored workflow with project-context dependencies.
---

# Projects

Projects knowledge covers broader project lifecycle, handoffs, scheduling, risk points, and delivery coordination patterns that are not yet specific enough to belong in the promoted Order Execution domain.

## Focus Areas

- Project lifecycle beyond the current order-execution lane
- Sales to project handoff patterns
- Scheduling and delivery coordination
- Installation and closeout patterns
- Risk patterns and escalation points
- Agent-assisted project coordination

## Current Pages

No standalone project-domain pages exist yet after the bounded order-execution pilot migration.

## Related Order Execution Pages

The first post-close project workflow pages now live in [[../order-execution/index|Order Execution]]:

- [[../order-execution/close-won-to-delivery-workflow|Close Won To Delivery Workflow]]
- [[../order-execution/order-execution-readiness-agent-requirements|Order Execution Readiness Agent Requirements]]
- [[../order-execution/order-execution-state-model|Order Execution State Model]]
- [[../order-execution/order-execution-transition-gate-rules|Order Execution Transition Gate Rules]]

[[../sales/freight-install-quote-readiness|Freight And Install Quote Readiness]] remains stored in `sales`, but order-execution pages should treat its reviewed F&I assumptions as part of the handoff context that prevents post-close reconstruction.

[[../sales/proposal-package-readiness|Proposal Package Readiness]] also remains stored in `sales`, but broader project lifecycle pages should treat its room context, design assets, vendor branches, proposal delivery event, and handoff assumptions as project context that should not be rediscovered later.

## Starter Pages To Add

- `project-lifecycle.md`
- `handoff-checklist.md`
- `delivery-and-installation.md`

Add these only when a source-backed or answerability-driven project page does not already belong in `order-execution`, `sales`, `service`, or another stronger lane.

## Maintenance Notes

- Check this index before creating new pages in this domain.
- Keep claims source-backed and link to related domains when workflows cross boundaries.
- Leave new pages in Draft until reviewed.
