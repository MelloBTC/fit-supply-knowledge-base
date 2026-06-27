# Project Context - Fit Supply Knowledge Base

## Purpose

The Fit Supply Knowledge Base is a structured LLM Wiki for designing a target-state knowledge system for a commercial fitness equipment distributor, using Fit Supply as the concrete example business.

The goal is not just to collect documents or mirror current operations. The goal is to turn source material, completed roadmap work, and Fit Supply-informed examples into traceable, maintained knowledge that can support future AI agents and show what an agent-ready distributor operating system could look like.

## Current Phase

**Phase**: Target-state skeleton and source-discovery setup

The current work is focused on:

- Establishing the folder structure.
- Defining governance and frontmatter rules.
- Creating domain index pages.
- Setting up agent instructions and wiki-mode behavior.
- Framing the wiki as a target-state exemplar before importing roadmap material.
- Incorporating completed work from `fast-os-capability-roadmap` without duplicating active work in `fast-os-knowledge-base`.
- Avoiding premature content synthesis before source handling and knowledge scope are clear.

## Source Model

- `raw/` contains original material and should preserve source context.
- `wiki/` contains synthesized pages that are easier to navigate and reuse.
- Every important wiki claim should point back to a source, a first-party note, or a documented provenance explanation.
- Roadmap-derived material should be classified before synthesis so target-state designs are not mistaken for current Fit Supply operations.
- `fast-os-knowledge-base` is the active home for catalog/schema risk, equipment answerability, source manifest pattern, validation gates, and repo-boundary options for commercial equipment knowledge. This repo should not replicate that work; it should consume mature outputs later if they fit the Fit Supply target-state wiki.

## Knowledge Scope

The default scope for this project is `target-state`.

Use these scope labels to prevent false confidence:

- `target-state`: the designed future-state operating model or knowledge structure.
- `reference-pattern`: a reusable commercial fitness distributor pattern informed by Fit Supply examples.
- `design-hypothesis`: a plausible pattern that still needs validation or stronger sourcing.
- `current-state`: how Fit Supply actually operates today. Keep this available but do not make it a major workstream until target-state design is mature.

## Domain Priorities

The `equipment` domain is important because equipment taxonomy, specs, compatibility, condition, and manufacturer details are central to commercial fitness distribution work. However, deep catalog/schema and equipment-answerability contract work belongs upstream in `fast-os-knowledge-base` until that work is mature enough to evaluate for inclusion here.

The other domains exist to connect equipment knowledge to real business workflows:

- `sales` connects products to customer needs, quoting, and proposals.
- `design` connects equipment to spaces, layouts, and planning decisions.
- `projects` connects sold work to delivery and handoffs.
- `service` connects equipment to maintenance, parts, and support.
- `company` provides example-business context.
- `governance` keeps the system reliable.
- Additional domains should be added when the roadmap inventory shows workflow areas that do not fit the starter skeleton.

## Working Boundaries

- Keep the structure simple until real source material reveals the need for more complexity.
- Treat the current domain list as provisional; expand it when the roadmap inventory shows missing workflow areas.
- Prefer improving existing pages and links over creating duplicates.
- Treat uncertain information as uncertain.
- Do not promote pages beyond `Draft` without a clear review action.
- Avoid turning raw notes into polished claims without provenance.
- Do not spend significant time documenting `current-state` until the target-state model is better developed.
- Do not duplicate active catalog/schema risk, equipment answerability, source manifest, validation gate, or repo-boundary work owned by `fast-os-knowledge-base`.

## Near-Term Next Step

The next durable step is to synthesize the strongest completed `fast-os-capability-roadmap` operating-model, macro-workflow, agent-candidate, and case-backed workflow artifacts into OKF/LLM Wiki pages. Treat commercial equipment knowledge-layer work as an upstream dependency to revisit after `fast-os-knowledge-base` reaches a useful maturity point.
