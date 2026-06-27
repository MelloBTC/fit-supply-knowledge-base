---
name: fit-supply-llm-wiki-schema
description: Structure, conventions, and governance for the Fit Supply LLM Wiki knowledge base. Follows Open Knowledge Format principles and LLM Wiki best practices.
---

# Fit Supply LLM Wiki – Structure & Schema (v0.1)

**Purpose**  
This document defines the structure, conventions, and governance for Fit Supply’s enterprise knowledge base. It is designed as a full **LLM Wiki** (`raw/` sources + compiled, interlinked wiki pages) following the methodology in the `open-knowledge-format` repository.

The knowledge base will catalogue Fit Supply’s systems, operating patterns, best practices, equipment knowledge, and workflows so it can eventually power internal agents and support business operations.

**Core Principles** (drawn from open-knowledge-format repo)
- Knowledge compounds over time rather than being re-derived.
- Strong provenance and traceability.
- Clear taxonomy and bidirectional linking.
- Built-in governance for freshness and quality.
- Agent-accessible while remaining human-usable.

---

## 1. LLM Wiki Architecture
fit-supply-knowledge-base/
├── raw/                          # Immutable source material
│   ├── documents/                # Existing docs, PDFs, notes, NetSuite exports
│   ├── research/                 # External research, manufacturer specs
│   └── imports/                  # Structured imports (equipment lists, etc.)
├── wiki/                         # Compiled, maintained knowledge
│   ├── index.md                  # Master index
│   ├── governance/               # Schema, rules, maintenance processes
│   ├── company/                  # Company overview, operations
│   ├── sales/                    # Sales processes, customer types
│   ├── design/                   # Space planning, layouts
│   ├── equipment/                # Equipment taxonomy & specs (core)
│   ├── projects/                 # Project lifecycle & workflows
│   ├── service/                  # Maintenance & support
│   └── knowledge-base/           # Meta knowledge about this wiki
├── schema.md                     # This file
├── AGENTS.md                     # Agent instructions
└── README.md
text**Key Concepts**
- `raw/` = source of truth for original material (never edit directly after import).
- `wiki/` = synthesized, interlinked, maintained knowledge.
- Every compiled page in `wiki/` should trace back to sources in `raw/`.

---

## 2. Top-Level Domain Structure

| Domain            | Focus Areas                                                              | Priority |
|-------------------|--------------------------------------------------------------------------|----------|
| **company**       | Business model, history, differentiators, roles, values                  | High     |
| **sales**         | Lead qualification, customer personas, quoting, financing, proposals     | High     |
| **design**        | Space planning, 2D/3D workflows, common layouts by facility type         | High     |
| **equipment**     | Taxonomy, specifications, new vs used, compatibility                     | Highest  |
| **projects**      | End-to-end project lifecycle, handoffs, timelines, risk patterns         | High     |
| **service**       | Maintenance contracts, service workflows, parts, technician coordination | High     |
| **governance**    | Knowledge operations, review processes, freshness, conflict boundaries   | High     |
| **knowledge-base**| How to use this wiki, contribution guidelines, agent instructions        | Medium   |

Each domain contains an `index.md` + individual concept pages.

---

## 3. Standard Frontmatter Template (OKF-aligned)

```yaml
---
title: 
type:                    # Concept | Process | Equipment | Customer-Persona | Workflow | Governance
domain:                  # equipment | sales | design | service | etc.
status:                  # Draft | Reviewed | Approved | Deprecated
last_reviewed: 
reviewed_by: 
sources:                 # List of raw/ paths or external references
related:                 # [[wikilinks]] to other key pages
tags: 
provenance_notes: 
---

4. Naming, Linking & Organization Conventions

Use Title Case for page titles and [[wikilinks]].
Prefer specific, descriptive names.
Create relationship pages when many-to-many connections exist.
Keep pages focused (one primary concept per page).


5. Governance & Maintenance Rules
Ownership

Domain owners assigned once skeleton is live.
Initial ownership defaults to creator until transferred.

Update Process

Proposed changes go through lightweight review (especially equipment specs and processes).
Reference the “knowledge change conflict boundary” concept when updates affect multiple areas.

Freshness Expectations

Equipment models & specs: Review every 6 months or on major manufacturer updates.
Processes & best practices: Review annually or after significant operational changes.
High-traffic pages: More frequent review.

Deprecation

Old pages move to status: Deprecated with link to replacement.


6. Agent Access & Context
This wiki is designed to support AI agents:

Pages should be self-contained with clear summaries.
Consistent structure + wikilinks enable GraphRAG-style traversal.
AGENTS.md contains specific instructions for agents.
Context contracts can be added later for specific agent roles.

---
