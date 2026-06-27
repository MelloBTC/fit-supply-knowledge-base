# fit-supply-knowledge-base

Target-state LLM Wiki for a commercial fitness equipment distributor, using Fit Supply as the concrete example business.

This repository contains the structured knowledge base for distributor operations, best practices, equipment knowledge, agentic workflow design, and future AI-agent support. It is designed to become a source-backed, agent-accessible wiki that can later be adapted for Fit Supply owner/staff contribution if the system becomes valuable to them.

**Status**: Target-state skeleton and source-discovery setup. The structure, governance rules, and import process are being established before broad content synthesis.

## Start Here

Read these files in order:

1. [AGENTS.md](AGENTS.md) - Operating instructions for AI agents.
2. [PROJECT_CONTEXT.md](PROJECT_CONTEXT.md) - Project purpose, phase, and current boundaries.
3. [schema.md](schema.md) - Wiki structure, page conventions, scope labels, and governance rules.
4. [wiki/index.md](wiki/index.md) - Root navigation for compiled wiki content.

## Repository Structure

```text
fit-supply-knowledge-base/
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

Build the target-state wiki foundation first: domain indexes, governance rules, provenance habits, answerability targets, roadmap import mapping, and equipment ontology foundations. Add business content after the source and classification pattern is clear enough to avoid false progress.
