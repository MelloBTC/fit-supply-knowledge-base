---
title: Roadmap Import Plan
type: Process
domain: knowledge-base
knowledge_scope: target-state
status: Draft
last_reviewed:
reviewed_by:
sources:
  - PROJECT_CONTEXT.md
  - schema.md
related:
  - [[agent-answerability-targets|Agent Answerability Targets]]
  - [[domain-model-review|Domain Model Review]]
  - [[../sales/source-aware-lead-intake-routing|Source-Aware Lead Intake And Routing]]
  - [[../governance/source-manifest|Source Manifest]]
  - [[../sales/hunter-sales-existing-multifamily-pattern|Hunter Sales Existing Multifamily Pattern]]
  - [[../index|Fit Supply Knowledge Base Index]]
agent_answerability:
  - How should roadmap artifacts be evaluated before becoming wiki pages?
  - Which classification fields should be captured during import planning?
tags:
  - import-plan
  - roadmap
  - source-discovery
provenance_notes: Initial process for read-only inventory of fast-os-capability-roadmap before importing or synthesizing content.
---

# Roadmap Import Plan

This page defines the process for reviewing `fast-os-capability-roadmap` before importing or converting material into this target-state LLM Wiki.

## Principle

Do not bulk-copy roadmap files into compiled wiki truth. First inventory, classify, and decide whether each artifact should become raw source material, a synthesized wiki page, an answerability target, a governance pattern, a deferred reference, or an upstream dependency.

## Inventory Fields

For each candidate roadmap artifact, capture:

- Source path
- Working title
- Summary
- Recommended domain
- Recommended `knowledge_scope`
- Candidate wiki destination
- Agent answerability supported
- Sensitivity or review concerns
- Import recommendation
- Notes on whether the domain model should expand

## Import Recommendations

Use one of these recommendations:

- `import-raw`: preserve as source material in `raw/` before synthesis.
- `synthesize-wiki`: convert into one or more compiled wiki pages.
- `answerability-target`: use to refine agent answerability before content import.
- `governance-pattern`: use to strengthen schema, review, contribution, or validation rules.
- defer: keep out of the initial import because the artifact is weak, unrelated, or premature.
- `upstream-dependency`: do not replicate locally; track the upstream owner and revisit after that work matures.

## Scope Defaults

- Default to `target-state` for designed future workflows.
- Use `reference-pattern` for generalized commercial fitness distributor patterns.
- Use `design-hypothesis` when the roadmap artifact is useful but not yet validated.
- Use `current-state` only when the artifact explicitly describes actual Fit Supply operations.

## Non-Replication Boundary

Do not replicate active `fast-os-knowledge-base` work around catalog/schema risk, equipment answerability, source manifest pattern, validation gates, or repo-boundary options for commercial equipment knowledge.

If a roadmap artifact points into that active lane, classify it as `upstream-dependency` unless the user explicitly opens a small adaptation task. This repo should focus on incorporating already-completed `fast-os-capability-roadmap` operating-model, macro-workflow, agent-candidate, and case-backed workflow artifacts.

The starter `wiki/` folder structure is provisional. The roadmap inventory should influence the final domain model; do not force roadmap concepts into starter folders when the evidence shows they need a first-class domain or cross-domain lens.

## Current Inventory

The first read-only inventory is recorded at `raw/imports/fast-os-capability-roadmap-source-inventory.md`.

## Initial Synthesis Progress

Completed on 2026-06-27:

- FSCR-002 was synthesized into [[../company/commercial-fitness-distributor-operating-model|Commercial Fitness Distributor Operating Model]].
- FSCR-003 was synthesized into [[distributor-workflow-map|Distributor Workflow Map]].
- FSCR-006 was synthesized into [[agent-capability-map|Agent Capability Map]].
- FSCR-007 was selectively imported to `raw/imports/fast-os-capability-roadmap/regency-lead-to-closed-won-work-unit-decomposition-v1.md` and synthesized into [[../sales/lead-to-closed-won-workflow|Lead To Closed Won Workflow]].
- FSCR-008 was selectively imported to `raw/imports/fast-os-capability-roadmap/regency-close-won-to-delivery-workflow-decomposition-v1.md` and synthesized into [[../projects/close-won-to-delivery-workflow|Close Won To Delivery Workflow]].
- FSCR-009 was synthesized into [[../projects/order-execution-readiness-agent-requirements|Order Execution Readiness Agent Requirements]].
- FSCR-010 was synthesized into [[../projects/order-execution-state-model|Order Execution State Model]] and [[../governance/order-execution-transition-gate-rules|Order Execution Transition Gate Rules]].
- FSCR-012 was synthesized into [[../sales/hunter-sales-existing-multifamily-pattern|Hunter Sales Existing Multifamily Pattern]] as a `design-hypothesis` page without importing the machine-readable fixture bundle.
- FSCR-016 was classified from the roadmap lead-intake/source-routing artifact family and synthesized into [[../sales/source-aware-lead-intake-routing|Source-Aware Lead Intake And Routing]] without importing raw customer, pricing, quote, or NetSuite artifacts.
- FSCR-004 remains an `upstream-dependency` owned by `fast-os-knowledge-base`.

## Current Order-Execution Synthesis Result

The first domain model review is recorded in [[domain-model-review|Domain Model Review]].

1. Keep the top-level wiki domain model unchanged for now.
2. Treat `order-execution` as an active lens spanning `projects` and `governance`, not as a new domain.
3. Use [[../projects/order-execution-readiness-agent-requirements|Order Execution Readiness Agent Requirements]] for coordinator behavior and human-boundary expectations.
4. Use [[../projects/order-execution-state-model|Order Execution State Model]] for state definitions and transition concepts.
5. Use [[../governance/order-execution-transition-gate-rules|Order Execution Transition Gate Rules]] for blocker, warning, review, override, and evaluation policy.
6. Continue tracking the commercial equipment knowledge-layer memo as an `upstream-dependency` owned by `fast-os-knowledge-base`, not as local synthesis work.

## Current Source-Aware Lead Intake Result

FSCR-016 now has one compiled sales page: [[../sales/source-aware-lead-intake-routing|Source-Aware Lead Intake And Routing]].

This page is `target-state` because it synthesizes a future-state source-aware lead intake workflow from roadmap capability, taxonomy, data-model, research/enrichment, and case-study artifacts. It preserves customer/source evidence as source labels and workflow patterns without importing raw customer emails, quote PDFs, pricing, NetSuite exports, source-feed records, or private attachments.

Treat `source-intelligence`, `lead-intake`, and `lead-research` as active sales sub-lanes for now. Do not create a top-level `lead-intelligence` domain until validated page density and navigation pressure justify it.

## Current Hunter-Sales Synthesis Result

FSCR-012 now has one compiled sales page: [[../sales/hunter-sales-existing-multifamily-pattern|Hunter Sales Existing Multifamily Pattern]].

This page is intentionally `design-hypothesis`, not `target-state`, because the source family contains candidate policy defaults, synthetic scenarios, provisional validation labels, and fixture-readiness notes. Keep the machine-readable evaluator fixtures upstream unless evaluation discipline becomes the active local checkpoint.

Treat `hunter-sales` as a sales sub-lane for now. Do not create a top-level `lead-intelligence` or `prospecting` domain until validated compiled pages create stronger navigation pressure.

## Recommended Next Slice

If evaluation discipline becomes the priority, review FSCR-011 for order-execution gate fixtures or the FSCR-012 fixture bundle for hunter-sales policy evaluation. Otherwise, continue with a non-gated workflow family. After FSCR-016, the strongest next candidates are selective case-backed validation of source-aware lead intake with additional sanitized examples, or a governance bridge from wiki knowledge to future agent build requirements if no new examples are available.
