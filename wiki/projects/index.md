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
related:
  - [[../index|Fit Supply Knowledge Base Index]]
  - [[../governance/index|Governance]]
  - [[../knowledge-base/domain-model-review|Domain Model Review]]
  - [[close-won-to-delivery-workflow|Close Won To Delivery Workflow]]
  - [[order-execution-readiness-agent-requirements|Order Execution Readiness Agent Requirements]]
  - [[order-execution-state-model|Order Execution State Model]]
  - [[../governance/order-execution-transition-gate-rules|Order Execution Transition Gate Rules]]
  - [[../governance/agent-evaluation-fixtures|Agent Evaluation Fixtures]]
agent_answerability:
  - What belongs in the Projects domain?
  - Which starter pages should be created first for this domain?
tags:
  - domain-index
  - projects
provenance_notes: Starter domain index created during target-state skeleton setup; content areas are placeholders until source-backed pages are added.
---

# Projects

Projects knowledge covers the target-state lifecycle after a sale becomes work to deliver, including handoffs, scheduling, risk points, and completion patterns.

## Focus Areas

- Project lifecycle
- Sales to project handoff
- Scheduling and delivery coordination
- Installation and closeout
- Risk patterns and escalation points
- Agent-assisted project coordination

## Current Pages

- [[close-won-to-delivery-workflow|Close Won To Delivery Workflow]]
- [[order-execution-readiness-agent-requirements|Order Execution Readiness Agent Requirements]]
- [[order-execution-state-model|Order Execution State Model]]

## Active Lens

`order-execution` is the active synthesis lens inside this domain. The first order-readiness and execution-state pages now live under `projects`, with governance-heavy gate policy linked from [[../governance/order-execution-transition-gate-rules|Order Execution Transition Gate Rules]] and evaluation discipline linked from [[../governance/agent-evaluation-fixtures|Agent Evaluation Fixtures]].

Do not create a top-level `order-execution` domain yet. Reassess only after these pages and any next synthesis page create enough repeated navigation or ownership logic to justify the move.

## Starter Pages To Add

- `project-lifecycle.md`
- `handoff-checklist.md`
- `delivery-and-installation.md`

## Maintenance Notes

- Check this index before creating new pages in this domain.
- Keep claims source-backed and link to related domains when workflows cross boundaries.
- Leave new pages in Draft until reviewed.
