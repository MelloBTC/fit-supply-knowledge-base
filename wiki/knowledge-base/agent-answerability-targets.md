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
  - wiki/sales/source-aware-lead-intake-routing.md
  - wiki/company/commercial-fitness-distributor-operating-model.md
  - wiki/knowledge-base/distributor-workflow-map.md
  - wiki/knowledge-base/agent-capability-map.md
  - wiki/knowledge-base/wiki-to-agent-build-bridge.md
  - wiki/sales/hunter-sales-existing-multifamily-pattern.md
  - wiki/projects/order-execution-readiness-agent-requirements.md
  - wiki/projects/order-execution-state-model.md
  - wiki/governance/order-execution-transition-gate-rules.md
  - wiki/governance/agent-evaluation-fixtures.md
related:
  - [[../index|Fit Supply Knowledge Base Index]]
  - [[roadmap-import-plan|Roadmap Import Plan]]
  - [[domain-model-review|Domain Model Review]]
  - [[wiki-to-agent-build-bridge|Wiki To Agent Build Bridge]]
  - [[../equipment/index|Equipment]]
  - [[../sales/index|Sales]]
  - [[../projects/index|Projects]]
  - [[../company/commercial-fitness-distributor-operating-model|Commercial Fitness Distributor Operating Model]]
  - [[distributor-workflow-map|Distributor Workflow Map]]
  - [[agent-capability-map|Agent Capability Map]]
  - [[../sales/source-aware-lead-intake-routing|Source-Aware Lead Intake And Routing]]
  - [[../sales/lead-to-closed-won-workflow|Lead To Closed Won Workflow]]
  - [[../sales/hunter-sales-existing-multifamily-pattern|Hunter Sales Existing Multifamily Pattern]]
  - [[../projects/close-won-to-delivery-workflow|Close Won To Delivery Workflow]]
  - [[../projects/order-execution-readiness-agent-requirements|Order Execution Readiness Agent Requirements]]
  - [[../projects/order-execution-state-model|Order Execution State Model]]
  - [[../governance/order-execution-transition-gate-rules|Order Execution Transition Gate Rules]]
  - [[../governance/agent-evaluation-fixtures|Agent Evaluation Fixtures]]
agent_answerability:
  - What should future agents be able to answer or do using this knowledge base?
  - Which wiki domains should be built first to support useful agent behavior?
tags:
  - answerability
  - target-state
  - agent-design
provenance_notes: Initial scaffold refined after first roadmap synthesis pass from FSCR-002, FSCR-003, FSCR-006, FSCR-007, FSCR-008, FSCR-009, FSCR-010, FSCR-012, FSCR-013, and FSCR-016. Updated 2026-06-27 after the FSCR-012 hunter-sales validation-status checkpoint.
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

### Source-Aware Lead Intake And Routing

- Explain why lead source type should determine the first workflow route instead of treating every lead as the same CRM record.
- Distinguish service-created replacement signals, owner-forwarded project intelligence, inbound bid requests, formal project-intelligence feeds, referrals, lifecycle triggers, and low-confidence inquiries.
- Identify whether a lead is quote-ready, quote-plausible but incomplete, pursuit-worthy but not quote-ready, or low-confidence.
- Explain why source event, human curation, route decision, owner, next action, review event, outcome, and source-quality signal must be preserved separately.
- Route formal-feed and project-intelligence leads into research/enrichment when amenity relevance, buyer path, timing, or source confidence is not strong enough for outreach.

### Hunter Sales And Prospecting Policy

- Explain why target-account coverage is broader than lead or opportunity workflow.
- Identify when budget windows, manager changes, amenity clues, service signals, or source-origin events should create review packages rather than automatic outreach.
- Distinguish hard suppression, retirement, deprioritization, long-tail nurture, active reactivation review, and downstream conversion states.
- Explain why dealer prospecting policy should be stored as data with versioning, approvals, guardrails, audit, and human override records.
- Explain what the current real/sanitized hunter-sales examples validate: source-origin routing, service-created replacement signals, grouped-property review, and active-workflow duplicate blocking.
- Flag budget-window, prospecting no-response, manager-change, hard-stop scope, soft-negative response, and sensitive-account review rules as provisional until real or sanitized dealer examples promote, split, or correct them.
- Distinguish explicit hard stops from soft negative responses before suppression, nurture, or contact-correction behavior is inferred.

### Order-Execution Readiness And State

- Explain what an order-execution readiness coordinator should detect, classify, route, draft, preserve, monitor, recommend, request for review, and record.
- Distinguish blockers, warnings, informational facts, and monitors for order-execution state transitions.
- Identify when a missing fact blocks only the next unsafe action while safe parallel work can continue.
- Explain which human review boundaries apply to approval proof, PO mismatch, contract terms, payment, vendor order, customer promise, install release, completion, exception closure, and relationship-ready status.
- Explain when sales should be notified versus asked to make a customer-facing or trust-sensitive decision.

### Agent Evaluation Fixtures

- Explain how synthetic fixture families can test a future readiness evaluator before real customer data is loaded.
- Identify whether a future evaluator correctly classifies the active gate, blocker/warning/monitor/hold result, owner routing, rep visibility, safe parallel progress, human review boundary, and required trace event.
- Distinguish wiki-level evaluation discipline from product-side evaluator implementation, machine-readable fixture imports, schema, runners, and production traces.

### Upstream Dependency Boundary

- Flag equipment catalog, model-specific specification, price freshness, product compatibility, and equipment answerability questions as upstream dependencies owned by `fast-os-knowledge-base` until mature outputs are available for local evaluation.

### Wiki-To-Agent Build Bridge

- Explain when a compiled wiki workflow is mature enough to inform future build-facing agent requirements.
- Preserve the distinction between source-backed answerability, conceptual data-shape implications, and product implementation details.
- Identify workflow evidence, repeated decisions, required context, expected outputs, risk, human review, test evidence, evaluation, and observability questions before any implementation lane treats a workflow as build-ready.
- Say when a page is useful wiki knowledge but not yet ready for build planning because validation, human boundaries, data availability, or test evidence remain weak.

## Target Behavior Standard

A future agent should be able to:

- Answer from compiled `wiki/` pages first.
- Cite specific files or sections.
- Distinguish target-state patterns from actual current-state operations.
- Say when a question cannot yet be answered from available sources.
- Recommend the next source or page needed to improve answerability.

## Domain Model Review Outcome

The first domain model review is recorded in [[domain-model-review|Domain Model Review]]. It keeps the top-level schema stable for now, treats `order-execution` as an active lane inside `projects` and `governance`, treats `hunter-sales` as an active sales sub-lane, and defers first-class domains for `agent-workflows`, `operating-model`, `lead-intelligence`, `installed-base`, and `order-execution` until more compiled page density supports the move.
