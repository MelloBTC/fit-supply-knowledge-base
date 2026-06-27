---
title: Fit Supply Knowledge Base Index
type: Index
domain: knowledge-base
knowledge_scope: target-state
status: Draft
last_reviewed:
reviewed_by:
sources:
  - schema.md
  - PROJECT_CONTEXT.md
related:
  - [[governance/index|Governance]]
  - [[equipment/index|Equipment]]
  - [[knowledge-base/index|Knowledge Base]]
  - [[knowledge-base/domain-model-review|Domain Model Review]]
  - [[knowledge-base/wiki-to-agent-build-bridge|Wiki To Agent Build Bridge]]
  - [[company/commercial-fitness-distributor-operating-model|Commercial Fitness Distributor Operating Model]]
  - [[knowledge-base/distributor-workflow-map|Distributor Workflow Map]]
  - [[knowledge-base/agent-capability-map|Agent Capability Map]]
  - [[projects/order-execution-readiness-agent-requirements|Order Execution Readiness Agent Requirements]]
  - [[projects/order-execution-state-model|Order Execution State Model]]
  - [[governance/order-execution-transition-gate-rules|Order Execution Transition Gate Rules]]
  - [[sales/source-aware-lead-intake-routing|Source-Aware Lead Intake And Routing]]
  - [[sales/hunter-sales-existing-multifamily-pattern|Hunter Sales Existing Multifamily Pattern]]
  - [[current-state/index|Current State]]
agent_answerability:
  - Where should an agent start when navigating the target-state distributor knowledge base?
  - Which domain index should an agent read for a given workflow or knowledge area?
tags:
  - root-index
  - navigation
provenance_notes: Root index for the target-state Fit Supply LLM Wiki skeleton.
---

# Fit Supply Knowledge Base Index

This is the root navigation page for the Fit Supply LLM Wiki. Start here when orienting to the compiled knowledge in `wiki/`.

## Domains

- [[governance/index|Governance]] - Schema, review process, freshness rules, source manifests, and knowledge maintenance.
- [[company/index|Company]] - Example-business context, roles, and differentiators.
- [[sales/index|Sales]] - Sales processes, customer types, quoting, proposals, and financing.
- [[design/index|Design]] - Space planning, layouts, 2D/3D workflows, and facility design patterns.
- [[equipment/index|Equipment]] - Equipment taxonomy, specifications, compatibility, and model knowledge.
- [[projects/index|Projects]] - Project lifecycle, handoffs, timelines, and risk patterns.
- [[service/index|Service]] - Maintenance, support, service workflows, parts, and technician coordination.
- [[current-state/index|Current State]] - Deferred lane for actual Fit Supply current-state notes.
- [[knowledge-base/index|Knowledge Base]] - Instructions, answerability targets, contribution patterns, and meta knowledge about this wiki.

## First-Pass Roadmap Synthesis Pages

- [[company/commercial-fitness-distributor-operating-model|Commercial Fitness Distributor Operating Model]] - Parent lifecycle, roles, data-object spine, and validation posture.
- [[knowledge-base/distributor-workflow-map|Distributor Workflow Map]] - Cross-domain workflow map and synthesis/defer boundaries.
- [[knowledge-base/agent-capability-map|Agent Capability Map]] - Candidate capability clusters and human review boundaries.
- [[sales/source-aware-lead-intake-routing|Source-Aware Lead Intake And Routing]] - Source-aware workflow for preserving lead provenance, routing first action, and tracking outcomes.
- [[sales/lead-to-closed-won-workflow|Lead To Closed Won Workflow]] - Case-backed sales workflow from lead signal to closed-won boundary.
- [[sales/hunter-sales-existing-multifamily-pattern|Hunter Sales Existing Multifamily Pattern]] - Design-hypothesis sales pattern for existing multifamily prospecting, reactivation, nurture, and human-reviewed outreach policy.
- [[projects/close-won-to-delivery-workflow|Close Won To Delivery Workflow]] - Case-backed project workflow from approval to delivery, completion, and relationship continuity.
- [[knowledge-base/domain-model-review|Domain Model Review]] - First domain-structure checkpoint after roadmap synthesis, including the order-execution lens decision.
- [[knowledge-base/wiki-to-agent-build-bridge|Wiki To Agent Build Bridge]] - Reference-pattern bridge for translating mature wiki knowledge into future build-facing agent requirements without creating product schema or architecture.

## Order-Execution Synthesis Lane

- [[projects/order-execution-readiness-agent-requirements|Order Execution Readiness Agent Requirements]] - Readiness coordinator behavior, human boundaries, rep visibility, and data shape implications.
- [[projects/order-execution-state-model|Order Execution State Model]] - Target-state ladder from quote-ready through relationship-ready.
- [[governance/order-execution-transition-gate-rules|Order Execution Transition Gate Rules]] - Gate behavior, blockers, warnings, review boundaries, overrides, and evaluation expectations.

## Working Notes

- Treat `target-state` as the default knowledge scope.
- Prefer domain indexes before individual pages.
- Keep source-backed claims connected to `raw/` material, roadmap artifacts, or documented first-party knowledge.
- Leave pages in `Draft` until they have been reviewed.
- Expand the domain model when roadmap inventory reveals important workflow areas that do not fit the starter skeleton.
