---
title: Agent Answerability Targets
type: Answerability-Target
domain: knowledge-base
knowledge_scope: target-state
status: Draft
last_reviewed:
reviewed_by:
sources:
  - PROJECT_CONTEXT.md
  - schema.md
  - raw/imports/fast-os-capability-roadmap-source-inventory.md
  - wiki/company/commercial-fitness-distributor-operating-model.md
  - wiki/knowledge-base/distributor-workflow-map.md
  - wiki/knowledge-base/agent-capability-map.md
related:
  - [[../index|Fit Supply Knowledge Base Index]]
  - [[roadmap-import-plan|Roadmap Import Plan]]
  - [[../equipment/index|Equipment]]
  - [[../sales/index|Sales]]
  - [[../projects/index|Projects]]
  - [[../company/commercial-fitness-distributor-operating-model|Commercial Fitness Distributor Operating Model]]
  - [[distributor-workflow-map|Distributor Workflow Map]]
  - [[agent-capability-map|Agent Capability Map]]
  - [[../sales/lead-to-closed-won-workflow|Lead To Closed Won Workflow]]
  - [[../projects/close-won-to-delivery-workflow|Close Won To Delivery Workflow]]
agent_answerability:
  - What should future agents be able to answer or do using this knowledge base?
  - Which wiki domains should be built first to support useful agent behavior?
tags:
  - answerability
  - target-state
  - agent-design
provenance_notes: Initial scaffold refined after first roadmap synthesis pass from FSCR-002, FSCR-003, FSCR-006, FSCR-007, and FSCR-008.
---

# Agent Answerability Targets

This page defines the early target-state questions and tasks the knowledge base should eventually support. These targets should guide which roadmap artifacts are worth importing and which wiki pages should be created first.

## Why This Exists

A knowledge base that will power agents needs more than organized pages. It needs clear answerability goals: the questions, decisions, and workflows an agent should support with citations and appropriate confidence.

## Initial Target Areas

### Equipment and Catalog

- Identify the correct equipment category for a customer need.
- Explain important equipment attributes such as footprint, condition, compatibility, intended facility type, and lifecycle considerations.
- Compare equipment options at the taxonomy or category level before relying on model-specific facts.
- Surface source gaps or freshness concerns for model specifications.

### Sales and Qualification

- Identify what information is needed to qualify a commercial fitness opportunity.
- Map customer type, facility type, budget, timeline, and goals to next sales actions.
- Explain what information is needed before quoting or proposing equipment.
- Support handoff from sales discovery into design or project planning.

### Design and Space Planning

- Explain the inputs needed for layout or amenity planning.
- Connect facility type and customer goals to equipment mix considerations.
- Identify when design assumptions need human review.

### Project and Handoff

- Explain the target-state lifecycle from sale to delivery, installation, and closeout.
- Identify handoff information that should move between sales, design, project coordination, and service.
- Surface risk patterns, missing information, or escalation triggers.

### Service and Lifecycle

- Triage service or maintenance needs at a high level.
- Connect equipment type, warranty/parts needs, and service workflow.
- Identify when current-state or staff-validated information is required.

## Roadmap-Derived Additions

The first roadmap synthesis pass adds these more specific answerability targets:

### Operating Model And Lifecycle

- Explain the target-state distributor lifecycle from lead source through account expansion.
- Identify which domain owns a workflow stage and when a workflow crosses domain boundaries.
- Distinguish target-state operating design from current Fit Supply operations.

### Agent Capability Boundaries

- Explain why the first capability taxonomy should be source intelligence, research/enrichment, quote-readiness, follow-up state, site/project-context capture, approval/handoff readiness, order/install readiness, and completion/relationship continuity rather than generic sales, quote, install, or service agents.
- Identify which actions AI can observe, prepare, draft, recommend, or route, and which actions require human review.
- Surface schema families needed by a workflow without treating them as final implementation schema.

### Case-Backed Workflows

- Explain what must happen between a lead signal and closed-won before operations can safely act.
- Explain why closed-won, order-ready, delivery-ready, install-complete, and relationship-ready are different states.
- Identify what context must carry from sales into project execution so post-close work does not rediscover the same facts.

### Upstream Dependency Boundary

- Flag equipment catalog, model-specific specification, price freshness, product compatibility, and equipment answerability questions as upstream dependencies owned by `fast-os-knowledge-base` until mature outputs are available for local evaluation.

## Target Behavior Standard

A future agent should be able to:

- Answer from compiled `wiki/` pages first.
- Cite specific files or sections.
- Distinguish target-state patterns from actual current-state operations.
- Say when a question cannot yet be answered from available sources.
- Recommend the next source or page needed to improve answerability.

## Next Refinement Step

After human review of the first synthesis pages, run a domain model review before the next synthesis pass. Decide whether concepts such as `order-execution`, `agent-workflows`, `operating-model`, `lead-intelligence`, and `installed-base` deserve first-class homes because the roadmap evidence supports them, rather than forcing them into the starter folder structure.
