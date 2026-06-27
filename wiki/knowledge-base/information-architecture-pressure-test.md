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
  - wiki/index.md
  - wiki/knowledge-base/index.md
  - wiki/company/commercial-fitness-distributor-operating-model.md
  - wiki/sales/source-aware-lead-intake-routing.md
  - wiki/sales/lead-to-closed-won-workflow.md
  - wiki/sales/hunter-sales-existing-multifamily-pattern.md
  - wiki/sales/freight-install-quote-readiness.md
  - wiki/projects/close-won-to-delivery-workflow.md
  - wiki/projects/order-execution-readiness-agent-requirements.md
  - wiki/projects/order-execution-state-model.md
  - wiki/governance/order-execution-transition-gate-rules.md
  - wiki/governance/source-manifest.md
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
  - [[../sales/freight-install-quote-readiness|Freight And Install Quote Readiness]]
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
provenance_notes: Created as an information-architecture pressure test after the first roadmap synthesis pass. This page evaluates structure against fast-os-capability-roadmap evidence and records a navigation recommendation; it does not move folders or promote a new phase. Updated 2026-06-27 after the first IA-guided navigation cleanup, the FSCR-017 freight/install quote-readiness classification pass, and the no-move structure audit with a v0.4 target-structure proposal.
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
| Freight/install quote readiness | Lives before quote send, but depends on product handling, site context, freight/install rules, approval provenance, validity windows, and order-execution handoff. |
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
| Root index | Start page for humans and agents. Now points to the major navigation lenses before domain folders. |
| Knowledge Base index | Local hub for navigation lenses, import planning, answerability, structure governance, and build-readiness boundaries. |
| Domain indexes | Storage homes and local page lists. Useful, but not enough alone. |
| Distributor Workflow Map | Primary lifecycle navigation. Use before creating workflow pages. |
| Agent Capability Map | Primary agent-readiness navigation. Use before naming agents or build candidates. |
| Order Execution State Model | Primary readiness-state example. Use as the anti-false-progress model. |
| Domain Model Review | Records when a lane is or is not promoted into a domain. |
| Agent Evaluation Fixtures | Records evaluation-fixture and trace discipline without creating an implementation or new domain. |
| Information Architecture Pressure Test | Records the broader structure decision and migration criteria. |

## No-Move Structure Audit 2026-06-27

Josh re-raised the folder-structure question after the wiki gained enough compiled pages for the mismatch to become more visible. This audit keeps the current files in place and maps the current page set against the structure the content is trying to become.

Audit result:

1. The mismatch is real enough to name directly.
2. The mismatch is not yet strong enough to justify a full physical migration.
3. `order-execution` is the first credible pilot candidate if Josh chooses to test a folder promotion.
4. `lead-intelligence`, `quote-readiness`, `agent-readiness`, `installed-base`, and `accounts-and-sites` should remain named lanes until more validated pages exist.

### Page Density Snapshot

| Area | Current compiled shape | IA signal | Current decision |
| --- | --- | --- | --- |
| Root | One root index. | Working as the entry point for lens-first navigation. | Keep. |
| `knowledge-base` | Seven content pages plus an index. | Over-carrying navigation, answerability, roadmap import, build bridge, and structure-governance work. | Keep as control plane for now; likely later split some material into `agent-readiness` and `governance`. |
| `sales` | Four workflow pages plus an index. | Real density, but it contains three different lanes: lead intelligence, lead-to-close workflow, and quote readiness. | Keep as storage for now; do not let `sales` hide the active lanes. |
| `projects` | Three workflow pages plus an index. | Mostly order-execution material now. | Closest candidate for a pilot migration. |
| `governance` | Three governance pages plus an index. | Contains general source governance plus order-execution gate/evaluation governance. | Keep for now; if order-execution moves, decide whether gate rules move with it. |
| `company` | One operating-model page plus an index. | `company` is acting as a home for operating-model truth, not company current-state truth. | Keep until lifecycle, role, and value-stream pages multiply. |
| `design`, `equipment`, `service`, `current-state` | Index-only placeholders. | Important domains, but not yet enough compiled local pages to drive migration. | Keep quiet; equipment remains upstream-dependent for deep catalog/schema work. |

### Migration Matrix For Current Pages

| Current page | Current home | Conceptual lane | Lifecycle, readiness, or capability lens | Likely future home | Current action |
| --- | --- | --- | --- | --- | --- |
| `wiki/index.md` | Root | Root navigation | All lenses | Root | Keep. |
| `wiki/company/index.md` | `company` | Domain facet | Company/operating-model context | Domain facet or `operating-model` index later | Keep. |
| `wiki/company/commercial-fitness-distributor-operating-model.md` | `company` | Operating model | Parent lifecycle, roles, data-object spine | `operating-model` | Keep until operating-model pages multiply. |
| `wiki/sales/index.md` | `sales` | Domain facet | Sales, lead, quote, and handoff navigation | Domain facet or split lane indexes later | Keep. |
| `wiki/sales/source-aware-lead-intake-routing.md` | `sales` | Lead intelligence | Lead identification, source routing, research/enrichment | `lead-intelligence` | Keep until lead research, source quality, and routing pages multiply. |
| `wiki/sales/lead-to-closed-won-workflow.md` | `sales` | End-to-end workflow | Lead signal through approval and order-readiness boundary | `workflows` | Keep; likely moves only in a broader lifecycle migration. |
| `wiki/sales/hunter-sales-existing-multifamily-pattern.md` | `sales` | Lead intelligence / prospecting | Target coverage, reactivation, suppression, human review | `lead-intelligence` | Keep because the page remains `design-hypothesis`. |
| `wiki/sales/freight-install-quote-readiness.md` | `sales` | Quote readiness | Pricing/quote creation, F&I review, handoff continuity | `quote-readiness` | Keep until quote-readiness pages expand beyond F&I. |
| `wiki/design/index.md` | `design` | Domain facet | Layout/design workflow placeholder | Domain facet or `workflows`/`equipment` facet later | Keep. |
| `wiki/equipment/index.md` | `equipment` | Equipment ontology | Product taxonomy and source freshness | `equipment` | Keep; wait for upstream mature outputs. |
| `wiki/projects/index.md` | `projects` | Domain facet | Project/order-execution navigation | Domain facet or `order-execution` index later | Keep for now. |
| `wiki/projects/close-won-to-delivery-workflow.md` | `projects` | Order execution / workflow | Closed-won through delivery, install, relationship transition | `order-execution` or `workflows` | Candidate for order-execution pilot. |
| `wiki/projects/order-execution-readiness-agent-requirements.md` | `projects` | Order execution / agent readiness | Coordinator behavior, blockers, human review | `order-execution` | Candidate for order-execution pilot. |
| `wiki/projects/order-execution-state-model.md` | `projects` | Order execution | Quote-ready through relationship-ready state model | `order-execution` | Candidate for order-execution pilot. |
| `wiki/service/index.md` | `service` | Domain facet | Service/warranty/installed-base placeholder | Domain facet or `installed-base` later | Keep. |
| `wiki/current-state/index.md` | `current-state` | Current-state lane | Staff-validated operating truth | `current-state` | Keep quiet. |
| `wiki/governance/index.md` | `governance` | Governance facet | Review, source, freshness, conflict rules | `governance` | Keep. |
| `wiki/governance/source-manifest.md` | `governance` | Source governance | Source/provenance discipline | `governance` | Keep. |
| `wiki/governance/order-execution-transition-gate-rules.md` | `governance` | Order execution governance | Gate rules, blockers, warnings, overrides | `order-execution` or `governance` | Decide during pilot; this is the key split point. |
| `wiki/governance/agent-evaluation-fixtures.md` | `governance` | Agent evaluation / readiness | Fixture discipline, trace expectations, human review | `agent-readiness` or `governance` | Keep; do not move with order-execution unless scope widens. |
| `wiki/knowledge-base/index.md` | `knowledge-base` | Wiki control plane | Navigation, import, answerability, IA | `knowledge-base` or split control plane | Keep. |
| `wiki/knowledge-base/agent-answerability-targets.md` | `knowledge-base` | Agent readiness | Answerability standards across domains | `agent-readiness` | Keep until agent-readiness folder exists. |
| `wiki/knowledge-base/roadmap-import-plan.md` | `knowledge-base` | Import governance | Roadmap classification and synthesis process | `governance` or `knowledge-base` | Keep. |
| `wiki/knowledge-base/domain-model-review.md` | `knowledge-base` | Structure governance | Domain promotion decisions | `governance` or `knowledge-base` | Keep as paired IA evidence. |
| `wiki/knowledge-base/information-architecture-pressure-test.md` | `knowledge-base` | Structure governance | Folder migration criteria and target IA | `governance` or `knowledge-base` | Keep as canonical structure decision page. |
| `wiki/knowledge-base/wiki-to-agent-build-bridge.md` | `knowledge-base` | Agent readiness / build bridge | Build-readiness boundary and evidence standard | `agent-readiness` | Keep until multiple build-bridge pages exist. |
| `wiki/knowledge-base/distributor-workflow-map.md` | `knowledge-base` | Workflow map | Lifecycle spine from lead source to relationship expansion | `workflows` | Keep as primary navigation lens. |
| `wiki/knowledge-base/agent-capability-map.md` | `knowledge-base` | Agent capability map | Capability clusters and human review boundaries | `agent-readiness` | Keep as primary navigation lens. |

### v0.4 Target Structure Proposal

If a physical migration is approved later, the next structure should not be another department-first layout. The likely `v0.4` structure should be lane-first while preserving governance and current-state boundaries:

```text
wiki/
  index.md
  operating-model/
  workflows/
  lead-intelligence/
  quote-readiness/
  order-execution/
  equipment/
  accounts-and-sites/
  installed-base/
  agent-readiness/
  governance/
  knowledge-base/
  current-state/
```

This is a target proposal, not the active structure. In that model:

| Proposed folder | Role |
| --- | --- |
| `operating-model` | Parent lifecycle, role, value-stream, data-object, and distributor operating-model pages. |
| `workflows` | End-to-end lifecycle maps and cross-stage workflow pages that should not be owned by a department. |
| `lead-intelligence` | Source-aware lead intake, lead research, prospecting, target coverage, source quality, and outreach policy. |
| `quote-readiness` | Quote completeness, F&I readiness, pricing assumptions, proposal readiness, approval provenance, and quote-source freshness. |
| `order-execution` | Closed-won through order readiness, vendor order, site readiness, delivery, install, closeout, and relationship-ready state. |
| `equipment` | Equipment ontology, manufacturer/model/source-freshness knowledge, and compatibility once upstream work matures. |
| `accounts-and-sites` | Account, property, site, contact, management company, buyer-path, and relationship-memory knowledge. |
| `installed-base` | Installed asset context, warranty, service history, replacement triggers, parts, and relationship expansion. |
| `agent-readiness` | Agent answerability, capability maps, context contracts, build bridges, fixture discipline, evaluation, and human-boundary patterns. |
| `governance` | Schema, review process, source manifests, freshness, conflict handling, provenance, and promotion/deprecation rules. |
| `knowledge-base` | Remaining wiki operating instructions and navigation patterns that do not yet belong in governance or agent-readiness. |
| `current-state` | Staff-validated actual Fit Supply operating notes, kept separate from target-state design. |

### Pilot Migration Candidate

If Josh chooses to test a physical folder promotion, start with `order-execution`, not a full restructure.

The pilot candidate would likely include:

- `wiki/projects/close-won-to-delivery-workflow.md`.
- `wiki/projects/order-execution-readiness-agent-requirements.md`.
- `wiki/projects/order-execution-state-model.md`.
- Possibly `wiki/governance/order-execution-transition-gate-rules.md`, if the pilot treats gate policy as part of the order-execution lane rather than general governance.

Do not include `wiki/governance/agent-evaluation-fixtures.md` in that first move unless the scope explicitly becomes an `agent-readiness` migration. Do not include `wiki/sales/freight-install-quote-readiness.md`; it should stay in the quote-readiness lane until that lane has enough pages to promote.

## Migration Triggers

Do not move folders just because a term repeats. Move only when the current structure creates practical maintenance pain.

| Candidate Folder | Promote When |
| --- | --- |
| `wiki/order-execution/` | Order execution has enough pages that splitting between `projects` and `governance` repeatedly obscures state, owner, gate, evaluation, and readiness navigation. |
| `wiki/lead-intelligence/` | Source-aware lead intake, lead research, hunter sales, source quality, and prospecting policy have multiple validated pages with repeated cross-links and shared ownership. |
| `wiki/agent-readiness/` or `wiki/agent-workflows/` | Multiple workflow pages become mature enough to need shared context contracts, build-readiness reviews, fixture/eval summaries, and human-boundary contracts. |
| `wiki/operating-model/` | Lifecycle, roles, data-object spine, value streams, and cross-domain maps outgrow `company` and `knowledge-base`. |
| `wiki/installed-base/` | Service, warranty, parts, replacement, asset lifecycle, and relationship-expansion pages become sourced enough to need a shared home. |
| `wiki/quote-readiness/` or `wiki/pricing-readiness/` | Freight/install, tax, margin, financing, proposal package, pricing source freshness, and quote approval pages become validated enough that `sales` can no longer explain ownership, review, and source boundaries cleanly. |
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

The no-move structure audit is complete:

1. Keep the current physical folders stable unless Josh explicitly approves a pilot migration.
2. Treat `order-execution` as the first pilot candidate if the repo tests physical folder promotion.
3. Use the migration matrix above before moving any page.
4. Use `wiki/index.md` as the root lens path before browsing domain folders.
5. Use `wiki/knowledge-base/index.md` as the local hub for workflow, capability, structure, evaluation, and build-readiness lenses.
6. Use this page and [[domain-model-review|Domain Model Review]] before adding or moving any top-level folder.
7. When synthesizing the next non-gated roadmap family, repeat lifecycle, state/readiness, agent capability, evaluation/build-readiness, storage-domain fit, and domain-promotion classification before adding pages or moving folders.

The best next move is now a decision fork:

- If Josh wants to reorganize now, run a bounded `order-execution` pilot migration and update all wikilinks/frontmatter in the same checkpoint.
- If Josh wants more evidence first, continue with another non-gated roadmap workflow family and keep using the current folders as storage homes.

## Decision

Do not physically reorganize the wiki yet.

Do change the operating rule:

```text
start from lifecycle, capability, and readiness maps
then land pages in the least-bad current storage folder
and promote folders only when evidence creates real navigation pressure
```

This preserves simplicity while acknowledging Josh's concern: the starter folder structure is not the final answer. It is scaffolding while the better FAST OS-shaped information architecture emerges. The no-move audit makes the next likely structure visible without making the repo pay migration cost before a bounded pilot is approved.
