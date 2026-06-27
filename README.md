# fit-supply-knowledge-base

Target-state LLM Wiki for a commercial fitness equipment distributor, using Fit Supply as the concrete example business.

This repository contains the structured knowledge base for distributor operations, best practices, equipment knowledge, agentic workflow design, and future AI-agent support. It is designed to become a source-backed, agent-accessible wiki that can later be adapted for Fit Supply owner/staff contribution if the system becomes valuable to them.

**Status**: Target-state skeleton and first roadmap synthesis. The structure, governance rules, import process, and first compiled roadmap-derived pages are now in place.

## Start Here

Read these files in order:

1. [AGENTS.md](AGENTS.md) - Operating instructions for AI agents.
2. [PROJECT_CONTEXT.md](PROJECT_CONTEXT.md) - Project purpose, phase, and current boundaries.
3. [docs/session-handoff.md](docs/session-handoff.md) - Compact restart surface and recommended next action.
4. [schema.md](schema.md) - Wiki structure, page conventions, scope labels, and governance rules.
5. [wiki/index.md](wiki/index.md) - Root navigation for compiled wiki content.

## Repository Structure

```text
fit-supply-knowledge-base/
|-- docs/                 # Compact handoff and future project operating notes
|-- raw/                  # Original source material and import manifests
|   |-- documents/        # Existing docs, PDFs, notes, exported documents
|   |-- research/         # External research and manufacturer information
|   `-- imports/          # Structured imports and source inventories
|-- wiki/                 # Compiled, maintained knowledge
|   |-- index.md          # Root wiki index
|   |-- governance/       # Schema, rules, and maintenance process
|   |-- company/          # Example-business context
|   |-- sales/            # Sales processes, customer types, quoting
|   |-- design/           # Space planning and design workflows
|   |-- equipment/        # Equipment taxonomy and specs
|   |-- projects/         # Project lifecycle and handoffs
|   |-- service/          # Service, support, maintenance, parts
|   |-- current-state/    # Deferred lane for actual Fit Supply current-state notes
|   `-- knowledge-base/   # Meta knowledge about this wiki
|-- AGENTS.md
|-- PROJECT_CONTEXT.md
|-- schema.md
`-- README.md
```

## Working Model

- Store original material and import manifests in `raw/`.
- Synthesize durable knowledge into `wiki/`.
- Treat `target-state` as the default knowledge scope.
- Keep `current-state` available but quiet until the target-state model is mature.
- Cite source paths and related wiki pages in frontmatter.
- Keep updates incremental, traceable, and aligned with `schema.md`.

## Current Priority

The first domain model review is complete in `wiki/knowledge-base/domain-model-review.md`. Keep the top-level wiki domains stable for now, deepen `order-execution` as the next synthesis lane inside `projects` and `governance`, and revisit a dedicated top-level domain only after the next order-execution pages create enough compiled page density to justify it. Treat commercial equipment knowledge-layer work as an upstream dependency to revisit after `fast-os-knowledge-base` reaches a useful maturity point.
