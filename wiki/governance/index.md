---
title: Governance
type: Index
domain: governance
knowledge_scope: reference-pattern
status: Draft
last_reviewed:
reviewed_by:
sources:
  - schema.md
  - PROJECT_CONTEXT.md
  - raw/imports/fast-os-capability-roadmap-source-inventory.md
  - wiki/order-execution/index.md
related:
  - [[../knowledge-base/index|Knowledge Base]]
  - [[../index|Fit Supply Knowledge Base Index]]
  - [[../order-execution/index|Order Execution]]
  - [[../order-execution/order-execution-transition-gate-rules|Order Execution Transition Gate Rules]]
  - [[../knowledge-base/domain-model-review|Domain Model Review]]
  - [[agent-evaluation-fixtures|Agent Evaluation Fixtures]]
agent_answerability:
  - What belongs in the Governance domain?
  - Which starter pages should be created first for this domain?
tags:
  - domain-index
  - governance
provenance_notes: Starter domain index created during target-state skeleton setup; updated 2026-06-27 after order-execution transition gate rules moved into the promoted order-execution domain while evaluation fixture discipline stayed in governance.
---

# Governance

Governance covers the rules, review patterns, freshness expectations, source manifest conventions, and change boundaries that keep the knowledge base trustworthy.

## Focus Areas

- Schema and frontmatter conventions
- Knowledge scope classification
- Source manifest and import review patterns
- Review and approval process
- Freshness expectations
- Conflict handling and provenance rules
- Agent and contributor operating rules
- Evaluation fixture discipline and build-readiness boundaries

## Current Pages

- [[source-manifest|Source Manifest]]
- [[agent-evaluation-fixtures|Agent Evaluation Fixtures]]

## Related Order Execution Governance

[[../order-execution/order-execution-transition-gate-rules|Order Execution Transition Gate Rules]] now lives in the promoted [[../order-execution/index|Order Execution]] domain because it is specific to post-close state transitions. [[agent-evaluation-fixtures|Agent Evaluation Fixtures]] remains in governance because it defines broader synthetic-fixture, trace, and human-review discipline for future agent-supported workflows.

Keep broad review-process work separate from the order-execution lane until repeated patterns justify a general human-review boundary page.

## Starter Pages To Add

- `review-process.md`
- `freshness-policy.md`
- `knowledge-change-conflict-boundary.md`

## Maintenance Notes

- Check this index before creating new pages in this domain.
- Keep claims source-backed and link to related domains when workflows cross boundaries.
- Leave new pages in Draft until reviewed.
