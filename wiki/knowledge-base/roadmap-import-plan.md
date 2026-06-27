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
  - raw/imports/fast-os-capability-roadmap-source-inventory.md
  - wiki/sales/hunter-sales-existing-multifamily-pattern.md
related:
  - [[agent-answerability-targets|Agent Answerability Targets]]
  - [[domain-model-review|Domain Model Review]]
  - [[wiki-to-agent-build-bridge|Wiki To Agent Build Bridge]]
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
provenance_notes: Initial process for read-only inventory of fast-os-capability-roadmap before importing or synthesizing content. Updated 2026-06-27 after the FSCR-012 hunter-sales validation-status checkpoint.
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
- FSCR-012 was synthesized into [[../sales/hunter-sales-existing-multifamily-pattern|Hunter Sales Existing Multifamily Pattern]] as a `design-hypothesis` page without importing the machine-readable fixture bundle, then updated with a validation-status checkpoint from real/sanitized example pressure tests and provisional probe results.
- FSCR-013 was synthesized into [[wiki-to-agent-build-bridge|Wiki To Agent Build Bridge]] as a `reference-pattern` bridge without creating product schema, agent architecture, live tooling, or implementation specs.
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

This page is intentionally `design-hypothesis`, not `target-state`, because the source family contains candidate policy defaults, synthetic scenarios, provisional validation labels, and fixture-readiness notes. The 2026-06-27 validation-status checkpoint strengthens source-origin routing, service-created replacement signal handling, grouped-property review, and active-workflow duplicate blocking from real/sanitized examples. It also confirms that the remaining budget-window, no-response, manager-change, hard-stop scope, soft-negative, and sensitive-account probes remain provisional or split-required.

Keep the machine-readable evaluator fixtures upstream unless evaluation discipline becomes the active local checkpoint. Treat `hunter-sales` as a sales sub-lane for now. Do not create a top-level `lead-intelligence` or `prospecting` domain until validated compiled pages create stronger navigation pressure.

## Current Wiki-To-Agent Build Bridge Result

FSCR-013 now has one compiled knowledge-base page: [[wiki-to-agent-build-bridge|Wiki To Agent Build Bridge]].

This page is `reference-pattern` because it adapts a roadmap bridge from workflow decomposition to future product build inputs. It records how mature wiki knowledge can later become build-facing requirements while keeping product schema, agent architecture, live tooling, executable tests, and implementation specs out of this repo.

Treat `agent-workflows` as a knowledge-base answerability and bridge lens for now. Do not create a top-level `agent-workflows` domain until multiple bridge or context-contract pages create stronger ownership and navigation pressure.

## Recommended Next Slice

FSCR-013 closes the governance bridge checkpoint without opening implementation scope.

If evaluation discipline becomes the priority, review FSCR-011 for order-execution gate fixtures or the FSCR-012 fixture bundle for hunter-sales policy evaluation. Otherwise, the next hunter-sales move should capture one real or sanitized dealer example from the open validation list before promoting any remaining policy defaults. Source-aware lead intake should follow the same example-first rule before build-facing requirements. If no dealer examples are available, continue with a non-gated roadmap workflow family.
