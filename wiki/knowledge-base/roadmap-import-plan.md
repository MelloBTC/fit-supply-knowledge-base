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
  - [[../governance/source-manifest|Source Manifest]]
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

## Current Inventory

The first read-only inventory is recorded at `raw/imports/fast-os-capability-roadmap-source-inventory.md`.

## Recommended First Slice

1. Synthesize the dealer operating model and macro workflow map into target-state operating-model pages.
2. Synthesize the agent candidate inventory into an agent capability map and refined answerability targets.
3. Import raw copies of the Regency lead-to-closed-won and close-won-to-delivery workflow decompositions only when ready to build the first case-backed workflow pages.
4. Track the commercial equipment knowledge-layer memo as an `upstream-dependency` owned by `fast-os-knowledge-base`, not as local synthesis work.
