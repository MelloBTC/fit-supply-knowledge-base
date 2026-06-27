---
name: fit-supply-llm-wiki-schema
description: Structure, conventions, and governance for the Fit Supply target-state LLM Wiki knowledge base.
---

# Fit Supply LLM Wiki - Structure & Schema (v0.3)

## Purpose

This document defines the structure, conventions, and governance for a target-state LLM Wiki for a commercial fitness equipment distributor, using Fit Supply as the concrete example business. The repository is designed as an LLM Wiki: original source material and import manifests live in `raw/`, while synthesized, interlinked, maintained knowledge lives in `wiki/`.

The knowledge base will catalogue distributor systems, operating patterns, best practices, equipment knowledge, agentic workflows, and answerability targets so it can eventually support AI agents and practical business operations.

## Core Principles

- Design the target-state system first; do not over-invest in current-state documentation yet.
- Knowledge should compound over time rather than be re-derived.
- Every durable claim should have provenance.
- Compiled wiki pages should be easy for both humans and agents to navigate.
- Equipment knowledge needs strong taxonomy, compatibility, and freshness discipline.
- Governance should prevent false confidence, stale specs, and duplicated pages.
- The starter domain model is provisional and should expand when source inventory shows missing workflow areas.

## 1. LLM Wiki Architecture

```text
fit-supply-knowledge-base/
|-- raw/                          # Source material and import manifests
|   |-- documents/                # Existing docs, PDFs, notes, NetSuite exports
|   |-- research/                 # External research, manufacturer specs
|   `-- imports/                  # Structured imports and source inventories
|-- wiki/                         # Compiled, maintained knowledge
|   |-- index.md                  # Master index
|   |-- governance/               # Schema, rules, maintenance processes
|   |-- company/                  # Example-business context
|   |-- sales/                    # Sales processes and customer types
|   |-- design/                   # Space planning and layout workflows
|   |-- equipment/                # Equipment taxonomy and specs
|   |-- projects/                 # Project lifecycle and handoffs
|   |-- service/                  # Maintenance and support
|   |-- current-state/            # Deferred lane for actual current-state notes
|   `-- knowledge-base/           # Meta knowledge about this wiki
|-- AGENTS.md                     # Agent instructions
|-- PROJECT_CONTEXT.md            # Project purpose and current phase
|-- schema.md                     # This file
`-- README.md
```

### Key Concepts

- `raw/` preserves original material, source inventories, and import manifests.
- `wiki/` is the source of truth for synthesized, maintained knowledge.
- Every compiled page in `wiki/` should trace back to `raw/` files, external references, or clearly marked first-party knowledge.
- Roadmap-derived material should be classified before synthesis so target-state designs are not mistaken for current Fit Supply operations.
- When raw sources conflict, document the conflict instead of smoothing it away.

## 2. Top-Level Domain Structure

| Domain | Focus Areas | Priority |
| --- | --- | --- |
| `company` | Example-business context, roles, differentiators, stakeholder assumptions | High |
| `sales` | Lead qualification, customer personas, quoting, financing, proposals | High |
| `design` | Space planning, 2D/3D workflows, common layouts by facility type | High |
| `equipment` | Taxonomy, specifications, condition, compatibility, model knowledge | Highest |
| `projects` | End-to-end project lifecycle, handoffs, timelines, risk patterns | High |
| `service` | Maintenance contracts, service workflows, parts, technician coordination | High |
| `current-state` | Actual Fit Supply current-state notes, deferred until needed | Low |
| `governance` | Knowledge operations, review process, freshness, conflict boundaries | High |
| `knowledge-base` | How to use this wiki, contribution patterns, agent instructions, answerability targets | Medium |

Each domain should contain an `index.md` plus focused concept, process, equipment, workflow, or governance pages.

## 3. Knowledge Scope Labels

Use `knowledge_scope` to identify what kind of claim a page is making:

| Scope | Meaning | Default Use |
| --- | --- | --- |
| `target-state` | Designed future-state operating model or knowledge structure | Default for this project |
| `reference-pattern` | Reusable distributor pattern informed by Fit Supply examples | Use for generalized patterns |
| `design-hypothesis` | Plausible but not yet validated pattern | Use when useful but uncertain |
| `current-state` | How Fit Supply actually operates today | Use sparingly until target-state design matures |

Do not treat `target-state` or `reference-pattern` pages as proof of current Fit Supply practice.

## 4. Standard Frontmatter Template

Use this frontmatter for compiled wiki pages:

```yaml
---
title:
type:                  # Concept | Process | Equipment | Customer-Persona | Workflow | Governance | Index | Answerability-Target
domain:               # company | sales | design | equipment | projects | service | current-state | governance | knowledge-base
knowledge_scope:       # target-state | reference-pattern | design-hypothesis | current-state
status:                # Draft | Reviewed | Approved | Deprecated
last_reviewed:
reviewed_by:
sources:               # raw/ paths, roadmap paths, external references, or first-party source notes
related:               # [[wikilinks]] to key related pages
agent_answerability:   # Optional list of questions/tasks this page helps agents answer or perform
tags:
provenance_notes:
---
```

### Field Expectations

- `title` should match the page heading.
- `type` should describe the page's role, not its folder.
- `domain` should identify the page's main home, even when it links across domains.
- `knowledge_scope` should default to `target-state` unless there is a reason to use another scope.
- `status` should remain `Draft` until a human review or explicit review process promotes it.
- `sources` should be specific enough for another agent or person to retrace the claim.
- `related` should link to pages that clarify dependencies, workflows, or adjacent concepts.
- `agent_answerability` should name the practical questions or tasks the page supports.
- `provenance_notes` should explain uncertainty, source gaps, conflicts, or synthesis choices.

## 5. Naming, Linking, and Organization Conventions

- Use descriptive filenames in lowercase kebab-case, such as `commercial-treadmills.md`.
- Use Title Case for page titles and display text in wikilinks.
- Prefer links to specific pages over broad folder references.
- Create relationship pages when many-to-many connections become important.
- Keep pages focused on one primary concept, process, equipment class, workflow, or answerability target.
- Avoid duplicating content across domains; link to the canonical page instead.
- Expand the domain model when roadmap inventory reveals important workflow areas that do not fit the starter skeleton.

## 6. Governance and Maintenance Rules

### Ownership

- Domain owners can be assigned once the skeleton is live.
- Initial ownership defaults to the creator until transferred.
- High-risk pages, especially equipment specs and operating procedures, should not be promoted without review.

### Update Process

- Start from the relevant domain `index.md`.
- Check existing pages before creating a new page.
- Add or update sources before making durable claims.
- Classify roadmap-derived material by `knowledge_scope` before synthesis.
- Reference this schema when changes affect multiple domains.
- Record conflicts or uncertain source quality in `provenance_notes`.

### Freshness Expectations

- Equipment models and specs: review every 6 months or after major manufacturer updates.
- Target-state workflows: review when roadmap assumptions or answerability targets change.
- Current-state pages: review after staff/owner validation or operational changes.
- High-traffic pages: review more frequently as usage patterns emerge.

### Deprecation

- Do not delete stale durable pages without review.
- Mark stale pages as `Deprecated`.
- Link deprecated pages to replacement pages when available.

## 7. Agent Access and Context

This wiki is designed to support AI agents:

- Agents should begin with `AGENTS.md`, `PROJECT_CONTEXT.md`, `schema.md`, and `wiki/index.md`.
- Agents should prioritize compiled `wiki/` pages over raw exploration.
- Raw sources and roadmap artifacts should be used to verify, enrich, or repair compiled pages.
- Pages should be self-contained enough to answer focused questions.
- Consistent frontmatter and wikilinks should enable graph-style traversal.
- Answerability targets should guide which content is worth synthesizing first.
- Context contracts can be added later for specific agent roles.
