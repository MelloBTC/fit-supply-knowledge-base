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
  - wiki/knowledge-base/information-architecture-pressure-test.md
  - wiki/knowledge-base/domain-model-review.md
  - wiki/sales/freight-install-quote-readiness.md
  - wiki/sales/proposal-package-readiness.md
  - wiki/order-execution/index.md
related:
  - [[governance/index|Governance]]
  - [[equipment/index|Equipment]]
  - [[order-execution/index|Order Execution]]
  - [[knowledge-base/index|Knowledge Base]]
  - [[knowledge-base/agent-answerability-targets|Agent Answerability Targets]]
  - [[knowledge-base/roadmap-import-plan|Roadmap Import Plan]]
  - [[knowledge-base/domain-model-review|Domain Model Review]]
  - [[knowledge-base/information-architecture-pressure-test|Information Architecture Pressure Test]]
  - [[knowledge-base/wiki-to-agent-build-bridge|Wiki To Agent Build Bridge]]
  - [[company/commercial-fitness-distributor-operating-model|Commercial Fitness Distributor Operating Model]]
  - [[knowledge-base/distributor-workflow-map|Distributor Workflow Map]]
  - [[knowledge-base/agent-capability-map|Agent Capability Map]]
  - [[sales/lead-to-closed-won-workflow|Lead To Closed Won Workflow]]
  - [[order-execution/close-won-to-delivery-workflow|Close Won To Delivery Workflow]]
  - [[order-execution/order-execution-readiness-agent-requirements|Order Execution Readiness Agent Requirements]]
  - [[order-execution/order-execution-state-model|Order Execution State Model]]
  - [[order-execution/order-execution-transition-gate-rules|Order Execution Transition Gate Rules]]
  - [[governance/agent-evaluation-fixtures|Agent Evaluation Fixtures]]
  - [[sales/source-aware-lead-intake-routing|Source-Aware Lead Intake And Routing]]
  - [[sales/hunter-sales-existing-multifamily-pattern|Hunter Sales Existing Multifamily Pattern]]
  - [[sales/freight-install-quote-readiness|Freight And Install Quote Readiness]]
  - [[sales/proposal-package-readiness|Proposal Package Readiness]]
  - [[current-state/index|Current State]]
agent_answerability:
  - Where should an agent start when navigating the target-state distributor knowledge base?
  - Which domain index should an agent read for a given workflow or knowledge area?
tags:
  - root-index
  - navigation
provenance_notes: Root index for the target-state Fit Supply LLM Wiki skeleton; updated 2026-06-27 to make IA navigation lenses explicit before domain folder browsing and to link the promoted order-execution pilot domain plus the proposal package readiness synthesis.
---

# Fit Supply Knowledge Base Index

This is the root navigation page for the Fit Supply LLM Wiki. Start here when orienting to the compiled knowledge in `wiki/`.

## Primary Navigation Lenses

Use these lenses before browsing folders when a question crosses departments, workflow states, or future agent boundaries.

- [[company/commercial-fitness-distributor-operating-model|Commercial Fitness Distributor Operating Model]] - Parent operating model, lifecycle, roles, and data-object spine.
- [[knowledge-base/distributor-workflow-map|Distributor Workflow Map]] - Primary lifecycle navigation from lead source through relationship expansion.
- [[knowledge-base/agent-capability-map|Agent Capability Map]] - Agent-readiness navigation by capability cluster and human review boundary.
- [[order-execution/order-execution-state-model|Order Execution State Model]] - Readiness/state navigation for avoiding false progress after approval.
- [[governance/agent-evaluation-fixtures|Agent Evaluation Fixtures]] - Evaluation-readiness lens for future testable agent behavior without opening product implementation.
- [[knowledge-base/wiki-to-agent-build-bridge|Wiki To Agent Build Bridge]] - Build-readiness bridge for mature wiki knowledge, not an implementation plan.
- [[knowledge-base/domain-model-review|Domain Model Review]] and [[knowledge-base/information-architecture-pressure-test|Information Architecture Pressure Test]] - Structure-governance pages to read before adding or moving additional top-level folders.

## Domains

- [[governance/index|Governance]] - Schema, review process, freshness rules, source manifests, and knowledge maintenance.
- [[company/index|Company]] - Example-business context, roles, and differentiators.
- [[sales/index|Sales]] - Sales processes, customer types, quoting, proposals, and financing.
- [[design/index|Design]] - Space planning, layouts, 2D/3D workflows, and facility design patterns.
- [[equipment/index|Equipment]] - Equipment taxonomy, specifications, compatibility, and model knowledge.
- [[projects/index|Projects]] - Broader project lifecycle, handoffs, timelines, and risk patterns.
- [[order-execution/index|Order Execution]] - Post-close readiness state, transition gates, delivery/install execution, completion, and relationship-ready handoff.
- [[service/index|Service]] - Maintenance, support, service workflows, parts, and technician coordination.
- [[current-state/index|Current State]] - Deferred lane for actual Fit Supply current-state notes.
- [[knowledge-base/index|Knowledge Base]] - Instructions, answerability targets, contribution patterns, and meta knowledge about this wiki.

## First-Pass Roadmap Synthesis Pages

- [[company/commercial-fitness-distributor-operating-model|Commercial Fitness Distributor Operating Model]] - Parent lifecycle, roles, data-object spine, and validation posture.
- [[knowledge-base/distributor-workflow-map|Distributor Workflow Map]] - Cross-domain workflow map and synthesis/defer boundaries.
- [[knowledge-base/agent-capability-map|Agent Capability Map]] - Candidate capability clusters and human review boundaries.
- [[sales/source-aware-lead-intake-routing|Source-Aware Lead Intake And Routing]] - Source-aware workflow for preserving lead provenance, routing first action, and tracking outcomes.
- [[sales/lead-to-closed-won-workflow|Lead To Closed Won Workflow]] - Case-backed sales workflow from lead signal to closed-won boundary.
- [[sales/freight-install-quote-readiness|Freight And Install Quote Readiness]] - Target-state quote-readiness workflow for freight, install, extraction, review/provenance, and handoff continuity.
- [[sales/proposal-package-readiness|Proposal Package Readiness]] - Target-state proposal-readiness workflow for project context, room uncertainty, design assets, visuals, quote/package alignment, delivery event, and follow-up state.
- [[sales/hunter-sales-existing-multifamily-pattern|Hunter Sales Existing Multifamily Pattern]] - Design-hypothesis sales pattern and validation-status checkpoint for existing multifamily prospecting, reactivation, source-origin routing, provisional probes, and human-reviewed outreach policy.
- [[order-execution/close-won-to-delivery-workflow|Close Won To Delivery Workflow]] - Case-backed order-execution workflow from approval to delivery, completion, and relationship continuity.
- [[knowledge-base/domain-model-review|Domain Model Review]] - Domain-structure checkpoint after roadmap synthesis, including the bounded order-execution pilot promotion.
- [[knowledge-base/information-architecture-pressure-test|Information Architecture Pressure Test]] - Structure checkpoint comparing department folders against roadmap workflow, readiness-state, and agent-capability navigation, with full `v0.4` migration still deferred.
- [[knowledge-base/wiki-to-agent-build-bridge|Wiki To Agent Build Bridge]] - Reference-pattern bridge for translating mature wiki knowledge into future build-facing agent requirements without creating product schema or architecture.

## Order Execution Domain

- [[order-execution/order-execution-readiness-agent-requirements|Order Execution Readiness Agent Requirements]] - Readiness coordinator behavior, human boundaries, rep visibility, and data shape implications.
- [[order-execution/order-execution-state-model|Order Execution State Model]] - Target-state ladder from quote-ready through relationship-ready.
- [[order-execution/order-execution-transition-gate-rules|Order Execution Transition Gate Rules]] - Gate behavior, blockers, warnings, review boundaries, overrides, and evaluation expectations.
- [[governance/agent-evaluation-fixtures|Agent Evaluation Fixtures]] - Synthetic-fixture, policy-parameter, trace, and review-boundary discipline for testing future readiness behavior before real customer data or product implementation work is opened.

## Working Notes

- Treat `target-state` as the default knowledge scope.
- Start from the primary navigation lenses for cross-domain workflow questions, then use domain indexes as storage homes.
- Keep source-backed claims connected to `raw/` material, roadmap artifacts, or documented first-party knowledge.
- Leave pages in `Draft` until they have been reviewed.
- Expand the domain model when roadmap inventory reveals important workflow areas that do not fit the starter skeleton.
- Treat domain folders as storage homes; `order-execution` is the first promoted lane from the folder-structure pilot, while broader v0.4 migration remains gated.
