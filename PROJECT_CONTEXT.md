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
- `projects` connects broader project lifecycle work and handoffs that are not yet owned by a more specific lane.
- `order-execution` owns the post-close readiness, gate, delivery/install execution, completion, and relationship-ready handoff lane.
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

The first durable roadmap synthesis pass now exists in `wiki/company/commercial-fitness-distributor-operating-model.md`, `wiki/knowledge-base/distributor-workflow-map.md`, `wiki/knowledge-base/agent-capability-map.md`, `wiki/sales/lead-to-closed-won-workflow.md`, and `wiki/order-execution/close-won-to-delivery-workflow.md`.

The order-execution synthesis lane now exists in `wiki/order-execution/order-execution-readiness-agent-requirements.md`, `wiki/order-execution/order-execution-state-model.md`, and `wiki/order-execution/order-execution-transition-gate-rules.md`.

The source-aware lead intake synthesis lane now exists in `wiki/sales/source-aware-lead-intake-routing.md`. It is a `target-state` page that classifies lead source events, quote-readiness distance, first-route decisions, source-specific first outputs, owner/action states, research/enrichment, and source-quality outcomes without importing raw customer, pricing, quote, NetSuite, or source-feed artifacts. The 2026-06-27 example-first captures synthesize the Bailey at Berkman ConstructConnect case as a human-curated formal-feed routing example and the Park at Rialto service-created replacement case as downstream source-to-quote/no-response outcome evidence, while keeping raw feed fields, formal-feed downstream outcomes, and final conversion/source-quality judgments as open validation gaps.

The freight/install quote-readiness synthesis lane now exists in `wiki/sales/freight-install-quote-readiness.md`. It is a `target-state` page that classifies F&I requirement detection, quote context inheritance, missing-context blockers, routine/exception routing, freight mode selection, draft freight/install/extraction estimates, human review/provenance, handoff continuity, actuals learning, and stale freight monitoring through the lifecycle, capability, readiness/state, evaluation/build-readiness, storage-domain, and domain-promotion lenses. It does not import raw NetSuite tasks, screenshots, quote PDFs, customer names, source amounts, pricing, or private logistics artifacts, and it keeps current rules, owners, thresholds, and actual-cost variance as validation needs before build-facing policy.

The first hunter-sales / prospecting synthesis lane now exists in `wiki/sales/hunter-sales-existing-multifamily-pattern.md`. It is intentionally a `design-hypothesis` page because the source family contains candidate policy defaults, provisional scenario labels, and fixture-readiness notes that still need dealer validation. The 2026-06-27 validation-status checkpoint strengthens source-origin routing, service-created replacement signals, grouped-property review, and active-workflow duplicate blocking from real/sanitized examples. A dealer-backed Regency capture now anchors duplicate-outreach blocking once an outbound response becomes active site visit, proposal, bid-collection, approved quote, closed-won, or order-readiness work. A soft-negative split-candidate capture clarifies that negative replies need classification before hard suppression, while budget-window, no-response, manager-change, hard-stop scope, soft-negative, and sensitive-account probes remain provisional or split-required.

The domain model review now exists in `wiki/knowledge-base/domain-model-review.md`. Its 2026-06-27 pressure recheck records `order-execution` as the first bounded promoted domain after Josh approved a pilot migration, keeps `source-intelligence`, `lead-intake`, and `hunter-sales` as active sales sub-lanes, and defers top-level domains for `agent-workflows`, `operating-model`, `lead-intelligence`, `quote-readiness`, `installed-base`, and `accounts-and-sites` until compiled page density or validated examples support the move.

The information-architecture pressure test now exists in `wiki/knowledge-base/information-architecture-pressure-test.md`. It compares the starter department-style folder structure against the `fast-os-capability-roadmap` lifecycle, readiness-state, and agent-capability evidence. The 2026-06-27 pilot migration promotes the order-execution candidate set into `wiki/order-execution/`, keeps the rest of the structure stable, and preserves the broader `v0.4` lane-first structure as a deferred proposal rather than an active migration.

The wiki-to-agent build bridge now exists in `wiki/knowledge-base/wiki-to-agent-build-bridge.md`. It is a `reference-pattern` page that explains how mature source-backed wiki knowledge can later become build-facing agent requirements while keeping product schema, agent architecture, live tooling, and implementation specs outside this repo.

The order-execution evaluation fixture discipline page now exists in `wiki/governance/agent-evaluation-fixtures.md`. It synthesizes FSCR-011 as target-state governance for synthetic fixtures, policy parameters, trace expectations, and human-review boundaries without importing the upstream machine-readable fixture bundle or opening product evaluator implementation.

The next durable step is to use the promoted `order-execution` domain as the pilot pattern, then continue with another non-gated roadmap synthesis pass or sales-validation example rather than expanding the folder migration. Use the lifecycle, capability, readiness/state, evaluation/build-readiness, storage-domain, and domain-promotion lenses before choosing a storage domain for any new roadmap family. Stay example-first for sales validation: capture downstream formal-feed outcome evidence, another explicit downstream lead-intake outcome, or the next dealer-backed hunter-sales example from the remaining open validation list before promoting policy defaults or moving either lane toward build-facing requirements. For hunter-sales, the highest-value remaining examples are budget-window target review, prospecting no-response, manager-change signal quality, scoped hard stops, real soft-negative responses, or sensitive-account review ownership. Treat commercial equipment knowledge-layer work as an upstream dependency to revisit after `fast-os-knowledge-base` reaches a useful maturity point. Treat freight/install quote-readiness as synthesized wiki knowledge, not a live pricing engine, rule source, or customer-facing quote updater.
