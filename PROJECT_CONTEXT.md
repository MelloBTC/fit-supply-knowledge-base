# Project Context - Fit Supply Knowledge Base

## Purpose

The Fit Supply Knowledge Base is a structured LLM Wiki for designing a target-state knowledge system for a commercial fitness equipment distributor, using Fit Supply as the concrete example business.

The goal is not just to collect documents or mirror current operations. The goal is to turn source material, completed roadmap work, and Fit Supply-informed examples into traceable, maintained knowledge that can support future AI agents and show what an agent-ready distributor operating system could look like.

The finished artifact should be useful as a knowledge base and guidebook for a commercial fitness distributor evaluating what it means to become AI-enabled. The FAST OS vision should be shown through credible operating-model detail, workflow design, and agent-support patterns rather than stated as overt marketing copy.

## Current Phase

**Phase**: Target-state skeleton and first roadmap synthesis

The current work is focused on:

- Establishing the folder structure.
- Defining governance and frontmatter rules.
- Creating domain index pages.
- Setting up agent instructions and wiki-mode behavior.
- Framing the wiki as a target-state exemplar before importing roadmap material.
- Incorporating completed work from `fast-os-capability-roadmap` without duplicating active work in `fast-os-knowledge-base`.
- Maintaining the first roadmap-derived synthesis pages while preserving source handling and knowledge-scope discipline.
- Reviewing whether the starter `wiki/` folder structure should evolve based on roadmap evidence before forcing new material into the initial skeleton.

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
- Let the stronger `fast-os-capability-roadmap` information architecture influence this repo's domain model; do not force roadmap concepts into starter folders when they deserve first-class homes.
- Prefer improving existing pages and links over creating duplicates.
- Treat uncertain information as uncertain.
- Do not promote pages beyond `Draft` without a clear review action.
- Avoid turning raw notes into polished claims without provenance.
- Do not spend significant time documenting `current-state` until the target-state model is better developed.
- Do not duplicate active catalog/schema risk, equipment answerability, source manifest, validation gate, or repo-boundary work owned by `fast-os-knowledge-base`.

## Near-Term Next Step

The first durable roadmap synthesis pass now exists in `wiki/company/commercial-fitness-distributor-operating-model.md`, `wiki/knowledge-base/distributor-workflow-map.md`, `wiki/knowledge-base/agent-capability-map.md`, `wiki/sales/lead-to-closed-won-workflow.md`, and `wiki/projects/close-won-to-delivery-workflow.md`.

The domain model review now exists in `wiki/knowledge-base/domain-model-review.md`. It keeps the top-level schema stable, promotes `order-execution` as the next active synthesis lane inside `projects` and `governance`, and defers top-level domains for `agent-workflows`, `operating-model`, `lead-intelligence`, and `installed-base` until compiled page density supports the move.

The next durable step is to review FSCR-009 and FSCR-010 from the roadmap inventory and synthesize order-execution readiness/state material without changing the top-level domain model yet. Treat commercial equipment knowledge-layer work as an upstream dependency to revisit after `fast-os-knowledge-base` reaches a useful maturity point.
