---
title: Source Manifest
type: Governance
domain: governance
knowledge_scope: reference-pattern
status: Draft
last_reviewed:
reviewed_by:
sources:
  - schema.md
  - PROJECT_CONTEXT.md
related:
  - [[../knowledge-base/roadmap-import-plan|Roadmap Import Plan]]
  - [[../knowledge-base/agent-answerability-targets|Agent Answerability Targets]]
agent_answerability:
  - How should sources be tracked before and after import?
  - What provenance fields should be captured for roadmap-derived knowledge?
tags:
  - source-manifest
  - provenance
  - governance
provenance_notes: Initial source manifest convention for target-state roadmap import and future source tracking.
---

# Source Manifest

A source manifest records where knowledge came from, why it matters, and how it should be used. This project should use manifests before importing roadmap material or promoting synthesized wiki pages.

## Manifest Fields

| Field | Purpose |
| --- | --- |
| `source_path` | Original file path or external reference. |
| `source_origin` | Repo, folder, owner, or external source. |
| `source_type` | Roadmap artifact, raw document, research, staff note, export, or external reference. |
| `recommended_domain` | Primary wiki domain for synthesis. |
| `knowledge_scope` | `target-state`, `reference-pattern`, `design-hypothesis`, or `current-state`. |
| `answerability_supported` | Questions or tasks the source helps future agents handle. |
| `sensitivity` | Any confidentiality, customer, pricing, staff, vendor, or operational risk. |
| `freshness` | Known date, likely review cycle, or freshness uncertainty. |
| `import_recommendation` | `import-raw`, `synthesize-wiki`, `answerability-target`, `governance-pattern`, `upstream-dependency`, or `defer`. |
| `notes` | Context, uncertainty, conflicts, or open questions. |

## Rule of Thumb

If an artifact is useful but idealized, classify it as `target-state` or `design-hypothesis`. Do not imply that it is current Fit Supply practice unless the source explicitly supports that claim.

If an artifact belongs to active work in another repo, mark it as `upstream-dependency` instead of recreating it locally. Current upstream-owned work includes `fast-os-knowledge-base` catalog/schema risk, equipment answerability, source manifest pattern, validation gates, and repo-boundary options for commercial equipment knowledge.

## Initial Manifest

The first manifest should inventory `fast-os-capability-roadmap` and live at `raw/imports/fast-os-capability-roadmap-source-inventory.md`.
