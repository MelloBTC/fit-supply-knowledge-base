---
title: Information Architecture Pressure Test
type: Governance
domain: knowledge-base
knowledge_scope: target-state
status: Draft
last_reviewed:
reviewed_by:
sources:
  - PROJECT_CONTEXT.md
  - docs/session-handoff.md
  - schema.md
  - raw/imports/fast-os-capability-roadmap-source-inventory.md
  - wiki/knowledge-base/domain-model-review.md
  - wiki/knowledge-base/distributor-workflow-map.md
  - wiki/knowledge-base/agent-capability-map.md
  - wiki/knowledge-base/wiki-to-agent-build-bridge.md
  - wiki/governance/agent-evaluation-fixtures.md
  - wiki/company/commercial-fitness-distributor-operating-model.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/06-agent-workflow-decomposition/macro-workflow-map-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/06-agent-workflow-decomposition/agent-candidate-inventory-v1.md
related:
  - [[domain-model-review|Domain Model Review]]
  - [[distributor-workflow-map|Distributor Workflow Map]]
  - [[agent-capability-map|Agent Capability Map]]
  - [[wiki-to-agent-build-bridge|Wiki To Agent Build Bridge]]
  - [[../governance/agent-evaluation-fixtures|Agent Evaluation Fixtures]]
  - [[roadmap-import-plan|Roadmap Import Plan]]
  - [[../company/commercial-fitness-distributor-operating-model|Commercial Fitness Distributor Operating Model]]
  - [[../sales/source-aware-lead-intake-routing|Source-Aware Lead Intake And Routing]]
  - [[../sales/hunter-sales-existing-multifamily-pattern|Hunter Sales Existing Multifamily Pattern]]
  - [[../projects/order-execution-state-model|Order Execution State Model]]
agent_answerability:
  - Is the current wiki folder structure still fit for the target-state FAST OS knowledge objective?
  - Which information architecture model best matches the fast-os-capability-roadmap evidence?
  - What should change now versus later before any folder migration?
tags:
  - information-architecture
  - domain-model
  - roadmap-derived
  - wiki-maintenance
provenance_notes: Created as an information-architecture pressure test after the first roadmap synthesis pass. This page evaluates structure against fast-os-capability-roadmap evidence and records a navigation recommendation; it does not move folders or promote a new phase.
---

# Information Architecture Pressure Test

This page evaluates whether the current `wiki/` folder structure is still the right structure for the target-state Fit Supply Knowledge Base now that the first `fast-os-capability-roadmap` synthesis pass has exposed the real shape of the content.

The short answer is:

```text
keep the current folders for now
but stop treating department folders as the only organizing model
```

The current structure is serviceable as a starter skeleton, but the roadmap evidence is more workflow-state, lifecycle, readiness, and agent-capability shaped than department shaped. The best next move is to add an explicit navigation layer before performing any physical folder migration.

## Review Question

The question is not only whether the folder names are good.

The deeper question is:

```text
what structure best helps a human or agent find the right source-backed answer,
understand the workflow state,
preserve evidence and uncertainty,
and avoid premature product or policy conclusions?
```

That standard matters because this repo is not merely a business handbook. It is a target-state knowledge system meant to support future AI agents and FAST OS workflow design.

## Current Structure

The current top-level wiki domains are:

```text
company
sales
design
equipment
projects
service
current-state
governance
knowledge-base
```

This is easy to explain to a human, and it maps to recognizable distributor functions. It also gives a safe home for early pages while the project is still Draft and source boundaries are still important.

The weakness is that active roadmap knowledge does not fit neatly into one department:

| Roadmap Pattern | Why Department Folders Strain |
| --- | --- |
| Source-aware lead intake | Starts in sales, but depends on source provenance, research/enrichment, outcome states, and source-quality learning. |
| Hunter sales | Lives in sales, but its real center is target coverage, policy validation, guardrails, and dealer judgment. |
| Lead-to-closed-won | Crosses lead source, discovery, site visit, design, product selection, proposal, follow-up, approval, and order-readiness. |
| Order execution | Starts after sales approval, but spans readiness state, vendor ordering, payment, site readiness, delivery, install, completion, and relationship continuity. |
| Agent capability map | Cuts across every department and is better understood as repeated work-unit clusters. |
| Equipment knowledge | Needs its own ontology, but deep answerability and source-manifest work remain upstream-owned for now. |

The current folders are therefore acceptable as storage homes, but insufficient as the primary mental model.

## Evidence From fast-os-capability-roadmap

The roadmap source inventory and compiled pages show three stronger organizing spines.

### Lifecycle Spine

The macro workflow map organizes work as:

```text
Lead Identification
-> Qualification
-> Discovery
-> Site Survey
-> Layout & Design
-> Equipment Selection
-> Pricing & Quote Creation
-> Proposal Assembly
-> Follow-Up & Objection Handling
-> Close & Procurement
-> Delivery & Install
-> Service & Warranty
-> Relationship Expansion
```

This is the strongest human navigation spine because it follows how distributor work moves from possible demand to supported customer outcome.

### State And Readiness Spine

The order-execution lane shows that the most important business distinction is often state, not department:

```text
quote-ready
-> approval-proof-ready
-> customer-committed / closed-won
-> order-ready
-> vendor-order-ready
-> site-ready
-> delivery-ready
-> install-scheduled
-> install-complete
-> relationship-ready
```

This spine is essential for avoiding false progress. A folder named `projects` does not by itself teach the difference between closed-won, order-ready, delivery-ready, install-complete, and relationship-ready.

### Agent-Capability Spine

The agent candidate inventory does not naturally form department agents. Its stronger shape is:

```text
source intelligence
-> research and enrichment
-> inbound quote-readiness
-> site-visit capture and debrief
-> project-context readiness
-> solution design support
-> quote and proposal readiness
-> follow-up and decision-state
-> approval and handoff readiness
-> order coordination
-> install readiness
-> completion and relationship continuity
-> playbook governance
```

This spine is the best agent-readiness view because it names repeated work-unit clusters and human review boundaries without prematurely naming product agents.

## Options Considered

### Option 1 - Keep Department Domains As Primary

This means continuing to organize primarily under `sales`, `design`, `equipment`, `projects`, and `service`.

| Strength | Weakness |
| --- | --- |
| Simple, familiar, and easy to explain. | Hides cross-stage workflows and repeated readiness/state patterns. |
| Keeps current pages stable. | Forces many pages to explain why they live in one folder while depending on several others. |
| Avoids migration churn. | Can make the repo feel like a business handbook instead of an agent-ready operating knowledge system. |

Decision: keep as storage for now, but not as the only navigation model.

### Option 2 - Migrate Immediately To Lifecycle Folders

Example:

```text
wiki/
  lifecycle/
  workflows/
  equipment/
  accounts-and-sites/
  installed-base/
  agent-readiness/
  governance/
  current-state/
```

| Strength | Weakness |
| --- | --- |
| Better matches the roadmap lifecycle and agent workflow decomposition. | Too early for a physical migration because several areas are still sparse or upstream-owned. |
| Makes cross-stage workflow pages easier to find. | Could create new empty folders that look more settled than the evidence supports. |
| Better supports future builder navigation. | Risks breaking simple domain navigation before the replacement model is proven. |

Decision: do not migrate immediately.

### Option 3 - Add Navigation Lenses Before Folder Migration

This keeps current folders but makes the primary navigation layers explicit:

```text
domain folders = storage homes
lifecycle map = workflow navigation
agent capability map = agent-readiness navigation
state/readiness pages = anti-false-progress navigation
domain model / IA pages = structure governance
```

| Strength | Weakness |
| --- | --- |
| Preserves current links and avoids churn. | Requires discipline so future agents do not rely only on folders. |
| Lets evidence accumulate before migration. | Some pages will continue to live in imperfect folders for a while. |
| Matches wiki-mode behavior: start from indexes and maps, not raw folder browsing. | Requires stronger root/index signposting. |

Decision: recommended.

### Option 4 - Promote First-Class Workflow Domains Now

Possible new folders:

```text
lead-intelligence
order-execution
agent-workflows
installed-base
operating-model
```

| Strength | Weakness |
| --- | --- |
| Names the strongest emerging concepts directly. | Risks promoting provisional or incomplete lanes into durable structure too soon. |
| Would reduce awkward cross-links for order execution and lead intelligence. | `lead-intelligence` and hunter-sales still need more examples; `installed-base` is not sourced enough locally. |
| Good eventual shape for some lanes. | Could make build-facing readiness look stronger than it is. |

Decision: defer until promotion triggers are met.

## Recommended Architecture For Now

Use a hybrid model:

```text
physical folders stay simple
navigation becomes workflow-first
promotion to new folders requires evidence
```

The current folders should be treated as storage domains, not as the complete information architecture.

| Layer | Role |
| --- | --- |
| Root index | Start page for humans and agents. Should point to the major navigation lenses. |
| Domain indexes | Storage homes and local page lists. Useful, but not enough alone. |
| Distributor Workflow Map | Primary lifecycle navigation. Use before creating workflow pages. |
| Agent Capability Map | Primary agent-readiness navigation. Use before naming agents or build candidates. |
| Order Execution State Model | Primary readiness-state example. Use as the anti-false-progress model. |
| Domain Model Review | Records when a lane is or is not promoted into a domain. |
| Agent Evaluation Fixtures | Records evaluation-fixture and trace discipline without creating an implementation or new domain. |
| Information Architecture Pressure Test | Records the broader structure decision and migration criteria. |

## Migration Triggers

Do not move folders just because a term repeats. Move only when the current structure creates practical maintenance pain.

| Candidate Folder | Promote When |
| --- | --- |
| `wiki/order-execution/` | Order execution has enough pages that splitting between `projects` and `governance` repeatedly obscures state, owner, gate, evaluation, and readiness navigation. |
| `wiki/lead-intelligence/` | Source-aware lead intake, lead research, hunter sales, source quality, and prospecting policy have multiple validated pages with repeated cross-links and shared ownership. |
| `wiki/agent-readiness/` or `wiki/agent-workflows/` | Multiple workflow pages become mature enough to need shared context contracts, build-readiness reviews, fixture/eval summaries, and human-boundary contracts. |
| `wiki/operating-model/` | Lifecycle, roles, data-object spine, value streams, and cross-domain maps outgrow `company` and `knowledge-base`. |
| `wiki/installed-base/` | Service, warranty, parts, replacement, asset lifecycle, and relationship-expansion pages become sourced enough to need a shared home. |
| `wiki/accounts-and-sites/` | Account, property, site, contact, management-company, buyer-path, and relationship-memory pages become cross-cutting enough that `sales`, `projects`, and `service` all depend on them. |

## Proposed Future Shape

If the evidence keeps moving in the current direction, the likely future structure is not pure department folders. A better mature structure may look like:

```text
wiki/
  index.md
  operating-model/
  workflows/
  lead-intelligence/
  order-execution/
  equipment/
  accounts-and-sites/
  installed-base/
  agent-readiness/
  governance/
  current-state/
```

This is a likely future shape, not the current migration plan.

The important idea is that `sales`, `projects`, and `service` may become lifecycle facets or page tags rather than the main organizing folders for every workflow page.

## What To Do Next

The next no-new-examples progress path is:

1. Keep the current physical folders stable.
2. Strengthen workflow-first navigation in the root and knowledge-base indexes.
3. Use this page and [[domain-model-review|Domain Model Review]] before adding or moving any top-level folder.
4. When synthesizing the next non-gated roadmap family, classify it against lifecycle, state/readiness, agent capability, and storage-domain fit.
5. Reassess folder migration only after at least one candidate lane meets its migration trigger.

The best next content slice without new examples is still open:

- A navigation cleanup pass now that FSCR-011 evaluation discipline is synthesized in [[../governance/agent-evaluation-fixtures|Agent Evaluation Fixtures]].
- Another non-gated roadmap workflow family if it strengthens the lifecycle or agent-readiness maps.
- A navigation cleanup pass if the immediate goal is making the existing wiki easier to traverse.

## Decision

Do not physically reorganize the wiki yet.

Do change the operating rule:

```text
start from lifecycle, capability, and readiness maps
then land pages in the least-bad current storage folder
and promote folders only when evidence creates real navigation pressure
```

This preserves simplicity while acknowledging Josh's concern: the starter folder structure is not the final answer. It is scaffolding while the better FAST OS-shaped information architecture emerges.
