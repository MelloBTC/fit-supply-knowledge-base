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
related:
  - [[../index|Fit Supply Knowledge Base Index]]
  - [[roadmap-import-plan|Roadmap Import Plan]]
  - [[../equipment/index|Equipment]]
  - [[../sales/index|Sales]]
  - [[../projects/index|Projects]]
agent_answerability:
  - What should future agents be able to answer or do using this knowledge base?
  - Which wiki domains should be built first to support useful agent behavior?
tags:
  - answerability
  - target-state
  - agent-design
provenance_notes: Initial answerability scaffold. Targets should be refined after read-only inventory of fast-os-capability-roadmap.
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

## Target Behavior Standard

A future agent should be able to:

- Answer from compiled `wiki/` pages first.
- Cite specific files or sections.
- Distinguish target-state patterns from actual current-state operations.
- Say when a question cannot yet be answered from available sources.
- Recommend the next source or page needed to improve answerability.

## Next Refinement Step

After the `fast-os-capability-roadmap` inventory, update this page with specific answerability targets found in existing roadmap artifacts.
