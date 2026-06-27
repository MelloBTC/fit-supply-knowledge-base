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
  - wiki/governance/agent-evaluation-fixtures.md
  - wiki/sales/freight-install-quote-readiness.md
related:
  - [[agent-answerability-targets|Agent Answerability Targets]]
  - [[domain-model-review|Domain Model Review]]
  - [[wiki-to-agent-build-bridge|Wiki To Agent Build Bridge]]
  - [[../sales/source-aware-lead-intake-routing|Source-Aware Lead Intake And Routing]]
  - [[../governance/source-manifest|Source Manifest]]
  - [[../governance/agent-evaluation-fixtures|Agent Evaluation Fixtures]]
  - [[../sales/hunter-sales-existing-multifamily-pattern|Hunter Sales Existing Multifamily Pattern]]
  - [[../sales/freight-install-quote-readiness|Freight And Install Quote Readiness]]
  - [[../index|Fit Supply Knowledge Base Index]]
agent_answerability:
  - How should roadmap artifacts be evaluated before becoming wiki pages?
  - Which classification fields should be captured during import planning?
tags:
  - import-plan
  - roadmap
  - source-discovery
provenance_notes: Initial process for read-only inventory of fast-os-capability-roadmap before importing or synthesizing content. Updated 2026-06-27 after the FSCR-017 freight/install quote-readiness synthesis without raw quote, pricing, task, or screenshot import.
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
- FSCR-011 was synthesized into [[../governance/agent-evaluation-fixtures|Agent Evaluation Fixtures]] as target-state governance without importing the upstream machine-readable fixture bundle or opening product evaluator implementation.
- FSCR-012 was synthesized into [[../sales/hunter-sales-existing-multifamily-pattern|Hunter Sales Existing Multifamily Pattern]] as a `design-hypothesis` page without importing the machine-readable fixture bundle, then updated with a validation-status checkpoint from real/sanitized example pressure tests, provisional probe results, a dealer-backed Regency active-workflow duplicate-block capture, and a soft-negative split-candidate capture.
- FSCR-013 was synthesized into [[wiki-to-agent-build-bridge|Wiki To Agent Build Bridge]] as a `reference-pattern` bridge without creating product schema, agent architecture, live tooling, or implementation specs.
- FSCR-016 was classified from the roadmap lead-intake/source-routing artifact family and synthesized into [[../sales/source-aware-lead-intake-routing|Source-Aware Lead Intake And Routing]] without importing raw customer, pricing, quote, or NetSuite artifacts; updated 2026-06-27 with a Bailey at Berkman formal-feed example capture and a Park at Rialto service-created replacement outcome capture.
- FSCR-017 was classified from the roadmap freight/install quote-readiness family and synthesized into [[../sales/freight-install-quote-readiness|Freight And Install Quote Readiness]] without importing raw NetSuite tasks, screenshots, quote PDFs, customer names, source amounts, pricing, or private logistics artifacts.
- FSCR-004 remains an `upstream-dependency` owned by `fast-os-knowledge-base`.

## Current Order-Execution Synthesis Result

The first domain model review is recorded in [[domain-model-review|Domain Model Review]].

1. Keep the top-level wiki domain model unchanged for now.
2. Treat `order-execution` as an active lens spanning `projects` and `governance`, not as a new domain.
3. Use [[../projects/order-execution-readiness-agent-requirements|Order Execution Readiness Agent Requirements]] for coordinator behavior and human-boundary expectations.
4. Use [[../projects/order-execution-state-model|Order Execution State Model]] for state definitions and transition concepts.
5. Use [[../governance/order-execution-transition-gate-rules|Order Execution Transition Gate Rules]] for blocker, warning, review, override, and transition policy.
6. Use [[../governance/agent-evaluation-fixtures|Agent Evaluation Fixtures]] for synthetic-fixture, policy-parameter, trace, and build-readiness evaluation discipline.
7. Continue tracking the commercial equipment knowledge-layer memo as an `upstream-dependency` owned by `fast-os-knowledge-base`, not as local synthesis work.

## Current Source-Aware Lead Intake Result

FSCR-016 now has one compiled sales page: [[../sales/source-aware-lead-intake-routing|Source-Aware Lead Intake And Routing]].

This page is `target-state` because it synthesizes a future-state source-aware lead intake workflow from roadmap capability, taxonomy, data-model, research/enrichment, and case-study artifacts. It preserves customer/source evidence as source labels and workflow patterns without importing raw customer emails, quote PDFs, pricing, NetSuite exports, source-feed records, or private attachments. The 2026-06-27 example-first captures use the Bailey at Berkman ConstructConnect case to preserve the distinction between original source event, human curation, rep task, research need, and open source-quality outcome, and the Park at Rialto service referral case to preserve source-to-quote/no-response outcome evidence without importing quote/pricing artifacts.

Treat `source-intelligence`, `lead-intake`, and `lead-research` as active sales sub-lanes for now. Do not create a top-level `lead-intelligence` domain until validated page density and navigation pressure justify it.

## Current Freight And Install Quote-Readiness Result

FSCR-017 now has one compiled sales page: [[../sales/freight-install-quote-readiness|Freight And Install Quote Readiness]].

This page is `target-state` because it synthesizes a future-state quote-readiness workflow from roadmap F&I capability, workflow decomposition, and lead-to-quote source artifacts. It classifies the family through lifecycle, capability, readiness/state, evaluation/build-readiness, storage-domain, and domain-promotion lenses before storing the result in `sales`.

The page preserves the boundary that F&I readiness is not a live pricing engine. It can support future answerability around requirement detection, quote context inheritance, missing blockers, routine/exception routing, freight modes, draft estimates, review/provenance, handoff continuity, actuals, and stale freight monitoring, but current freight rules, installer rules, approval owners, thresholds, and actual-cost variance still need validation before build-facing policy.

Keep `quote-readiness` as a sales sub-lane for now. Do not create a top-level `quote-readiness`, `pricing`, or `freight-install` domain until multiple validated quote readiness pages create real navigation pressure.

## Current Hunter-Sales Synthesis Result

FSCR-012 now has one compiled sales page: [[../sales/hunter-sales-existing-multifamily-pattern|Hunter Sales Existing Multifamily Pattern]].

This page is intentionally `design-hypothesis`, not `target-state`, because the source family contains candidate policy defaults, synthetic scenarios, provisional validation labels, and fixture-readiness notes. The 2026-06-27 validation-status checkpoint strengthens source-origin routing, service-created replacement signal handling, grouped-property review, and active-workflow duplicate blocking from real/sanitized examples. The dealer-backed Regency capture anchors the active-workflow duplicate-block guardrail once outbound response becomes site visit, proposal, bid-collection, approved quote, closed-won, or order-readiness work. The soft-negative split-candidate capture adds a compiled checklist for classifying negative replies before hard suppression, but neither capture promotes fixtures or dealer policy. Budget-window, no-response, manager-change, hard-stop scope, soft-negative, and sensitive-account probes remain provisional or split-required.

Keep the machine-readable evaluator fixtures upstream even after local evaluation-governance synthesis. Treat `hunter-sales` as a sales sub-lane for now. Do not create a top-level `lead-intelligence` or `prospecting` domain until validated compiled pages create stronger navigation pressure.

## Current Wiki-To-Agent Build Bridge Result

FSCR-013 now has one compiled knowledge-base page: [[wiki-to-agent-build-bridge|Wiki To Agent Build Bridge]].

This page is `reference-pattern` because it adapts a roadmap bridge from workflow decomposition to future product build inputs. It records how mature wiki knowledge can later become build-facing requirements while keeping product schema, agent architecture, live tooling, executable tests, and implementation specs out of this repo.

Treat `agent-workflows` as a knowledge-base answerability and bridge lens for now. Do not create a top-level `agent-workflows` domain until multiple bridge or context-contract pages create stronger ownership and navigation pressure.

## Recommended Next Slice

FSCR-017 closes the freight/install quote-readiness checkpoint without opening raw quote import, customer/pricing material, live pricing automation, customer-facing quote updates, or product implementation scope.

FSCR-011 is now closed as a local governance synthesis page, not a fixture import. The next order-execution move should be navigation cleanup, dealer validation of unresolved policy thresholds, or future build-lane handoff only after Josh explicitly opens that scope. Otherwise, continue the example-first rule before build-facing requirements: capture downstream outcome evidence for the formal-feed source-aware example, capture another explicit downstream lead-intake outcome, or capture the next dealer-backed hunter-sales example from the remaining open validation list before promoting any remaining policy defaults. If no dealer examples are available, continue with another non-gated roadmap workflow family after classifying it through the lifecycle, capability, readiness/state, evaluation/build-readiness, storage-domain, and domain-promotion lenses.
