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
  - wiki/index.md
  - wiki/order-execution/index.md
  - wiki/knowledge-base/domain-model-review.md
  - wiki/knowledge-base/distributor-workflow-map.md
  - wiki/knowledge-base/agent-capability-map.md
  - wiki/knowledge-base/wiki-to-agent-build-bridge.md
  - wiki/governance/agent-evaluation-fixtures.md
  - wiki/knowledge-base/index.md
  - wiki/company/commercial-fitness-distributor-operating-model.md
  - wiki/sales/source-aware-lead-intake-routing.md
  - wiki/sales/lead-to-closed-won-workflow.md
  - wiki/sales/hunter-sales-existing-multifamily-pattern.md
  - wiki/sales/freight-install-quote-readiness.md
  - wiki/sales/proposal-package-readiness.md
  - wiki/order-execution/close-won-to-delivery-workflow.md
  - wiki/order-execution/order-execution-readiness-agent-requirements.md
  - wiki/order-execution/order-execution-state-model.md
  - wiki/order-execution/order-execution-transition-gate-rules.md
  - wiki/governance/source-manifest.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/06-agent-workflow-decomposition/macro-workflow-map-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/06-agent-workflow-decomposition/agent-candidate-inventory-v1.md
related:
  - [[domain-model-review|Domain Model Review]]
  - [[distributor-workflow-map|Distributor Workflow Map]]
  - [[agent-capability-map|Agent Capability Map]]
  - [[wiki-to-agent-build-bridge|Wiki To Agent Build Bridge]]
  - [[../order-execution/index|Order Execution]]
  - [[../governance/agent-evaluation-fixtures|Agent Evaluation Fixtures]]
  - [[roadmap-import-plan|Roadmap Import Plan]]
  - [[../company/commercial-fitness-distributor-operating-model|Commercial Fitness Distributor Operating Model]]
  - [[../sales/source-aware-lead-intake-routing|Source-Aware Lead Intake And Routing]]
  - [[../sales/hunter-sales-existing-multifamily-pattern|Hunter Sales Existing Multifamily Pattern]]
  - [[../sales/freight-install-quote-readiness|Freight And Install Quote Readiness]]
  - [[../sales/proposal-package-readiness|Proposal Package Readiness]]
  - [[../order-execution/order-execution-state-model|Order Execution State Model]]
agent_answerability:
  - Is the current wiki folder structure still fit for the target-state FAST OS knowledge objective?
  - Which information architecture model best matches the fast-os-capability-roadmap evidence?
  - What should change now versus later before any folder migration?
tags:
  - information-architecture
  - domain-model
  - roadmap-derived
  - wiki-maintenance
provenance_notes: Created as an information-architecture pressure test after the first roadmap synthesis pass. Updated 2026-06-27 after the no-move structure audit and the bounded order-execution pilot migration. This page records structure decisions; it does not promote a product phase or import private operational artifacts.
---

# Information Architecture Pressure Test

This page evaluates whether the current `wiki/` folder structure is still the right structure for the target-state Fit Supply Knowledge Base now that the first `fast-os-capability-roadmap` synthesis pass has exposed the real shape of the content.

The short answer is:

```text
keep the starter folders mostly stable
promote order-execution as the first bounded workflow domain
keep the larger v0.4 lane-first migration deferred
```

The current structure is serviceable as a starter skeleton, but the roadmap evidence is more workflow-state, lifecycle, readiness, and agent-capability shaped than department shaped. The order-execution pilot is a controlled test of that better structure, not permission to reorganize everything at once.

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
order-execution
service
current-state
governance
knowledge-base
```

This is still close to the starter department model, with one important exception: `order-execution` is now a first-class workflow domain because the post-close readiness/state/gate pages had outgrown their split between `projects` and `governance`.

The remaining weakness is that active roadmap knowledge does not fit neatly into one department:

| Roadmap Pattern | Why Department Folders Strain |
| --- | --- |
| Source-aware lead intake | Starts in sales, but depends on source provenance, research/enrichment, outcome states, and source-quality learning. |
| Hunter sales | Lives in sales, but its real center is target coverage, policy validation, guardrails, and dealer judgment. |
| Lead-to-closed-won | Crosses lead source, discovery, site visit, design, product selection, proposal, follow-up, approval, and order-readiness. |
| Order execution | Starts after sales approval, but spans readiness state, vendor ordering, payment, site readiness, delivery, install, completion, and relationship continuity. This is now the pilot promoted domain. |
| Freight/install quote readiness | Lives before quote send, but depends on product handling, site context, freight/install rules, approval provenance, validity windows, and order-execution handoff. |
| Proposal package readiness | Lives before proposal send, but depends on project context, room uncertainty, design assets, visual review, quote/package alignment, proposal delivery, and follow-up state. |
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
| Keeps most current pages stable. | Forces many pages to explain why they live in one folder while depending on several others. |
| Avoids migration churn. | Can make the repo feel like a business handbook instead of an agent-ready operating knowledge system. |

Decision: keep as storage for most domains, but not as the only navigation model.

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
| Preserves most current links and avoids broad churn. | Requires discipline so future agents do not rely only on folders. |
| Lets evidence accumulate before migration. | Some pages will continue to live in imperfect folders for a while. |
| Matches wiki-mode behavior: start from indexes and maps, not raw folder browsing. | Requires strong root/index signposting. |

Decision: still recommended as the general rule.

### Option 4 - Promote First-Class Workflow Domains Selectively

Possible new folders:

```text
lead-intelligence
order-execution
agent-readiness
installed-base
operating-model
quote-readiness
```

| Strength | Weakness |
| --- | --- |
| Names the strongest emerging concepts directly. | Risks promoting provisional or incomplete lanes into durable structure too soon. |
| Reduces awkward cross-links when one lane is already coherent. | Some candidates still need more evidence and validation. |
| Lets the repo test a lane-first shape without moving everything. | Requires clear boundaries so a pilot does not become uncontrolled migration. |

Decision: promote only `order-execution` now.

## Recommended Architecture For Now

Use a hybrid model:

```text
physical folders stay simple except for the order-execution pilot
navigation becomes workflow-first
future folder promotion requires evidence
```

The current folders should be treated as storage domains, not as the complete information architecture.

| Layer | Role |
| --- | --- |
| Root index | Start page for humans and agents. Points to the major navigation lenses before domain folders. |
| Knowledge Base index | Local hub for navigation lenses, import planning, answerability, structure governance, and build-readiness boundaries. |
| Order Execution index | First promoted workflow-domain home for post-close readiness, state, gate, delivery/install execution, and handoff pages. |
| Domain indexes | Storage homes and local page lists. Useful, but not enough alone. |
| Distributor Workflow Map | Primary lifecycle navigation. Use before creating workflow pages. |
| Agent Capability Map | Primary agent-readiness navigation. Use before naming agents or build candidates. |
| Order Execution State Model | Primary readiness-state example. Use as the anti-false-progress model. |
| Domain Model Review | Records when a lane is or is not promoted into a domain. |
| Agent Evaluation Fixtures | Records evaluation-fixture and trace discipline without creating an implementation or agent-readiness domain. |
| Information Architecture Pressure Test | Records the broader structure decision and migration criteria. |

## Structure Audit And Pilot Result 2026-06-27

Josh re-raised the folder-structure question after the wiki gained enough compiled pages for the mismatch to become more visible. The audit first mapped the page set without moving files. Josh then approved a bounded `order-execution` pilot migration.

Pilot result:

1. The mismatch is real enough to name directly.
2. The mismatch is strong enough to promote only `order-execution` now.
3. The mismatch is not yet strong enough to justify a full physical migration.
4. `lead-intelligence`, `quote-readiness`, `proposal-readiness`, `agent-readiness`, `installed-base`, and `accounts-and-sites` should remain named lanes until more validated pages exist.

### Page Density Snapshot

| Area | Current compiled shape | IA signal | Current decision |
| --- | --- | --- | --- |
| Root | One root index. | Working as the entry point for lens-first navigation. | Keep. |
| `knowledge-base` | Navigation, answerability, roadmap import, build bridge, and structure-governance pages. | Still a control plane, with some future `agent-readiness` pressure. | Keep as control plane for now. |
| `sales` | Five workflow pages plus an index. | Real density, but it contains lead intelligence, lead-to-close workflow, hunter-sales, quote readiness, and proposal readiness. | Keep as storage for now; do not let `sales` hide active lanes. |
| `projects` | Index only after the pilot migration. | No longer carries order-execution pages; future project-lifecycle pages may still land here. | Keep quiet until new project-domain material appears. |
| `order-execution` | Four content pages plus an index. | Strongest first workflow-domain candidate; now promoted. | Use as the pilot domain and template for future lane-promotion discipline. |
| `governance` | Source manifest, evaluation fixture discipline, and an index. | General governance remains here; order-specific gate rules moved to order-execution. | Keep; do not move evaluation fixtures unless an `agent-readiness` migration is later approved. |
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
| `wiki/sales/proposal-package-readiness.md` | `sales` | Proposal readiness | Proposal assembly, project-context readiness, room/design asset review, visual accuracy, follow-up state | `quote-readiness`, `proposal-readiness`, or `workflows` | Keep until proposal/pricing/readiness pages multiply enough to create real navigation pressure. |
| `wiki/design/index.md` | `design` | Domain facet | Layout/design workflow placeholder | Domain facet or `workflows`/`equipment` facet later | Keep. |
| `wiki/equipment/index.md` | `equipment` | Equipment ontology | Product taxonomy and source freshness | `equipment` | Keep; wait for upstream mature outputs. |
| `wiki/projects/index.md` | `projects` | Domain facet | Broader project lifecycle placeholder after order-execution promotion | Domain facet or workflow facet later | Keep quiet until new project-domain material appears. |
| `wiki/order-execution/index.md` | `order-execution` | Promoted workflow domain | Closed-won through relationship-ready navigation | `order-execution` | Keep as pilot index. |
| `wiki/order-execution/close-won-to-delivery-workflow.md` | `order-execution` | Order execution / workflow | Closed-won through delivery, install, relationship transition | `order-execution` or broader `workflows` later | Moved in pilot. |
| `wiki/order-execution/order-execution-readiness-agent-requirements.md` | `order-execution` | Order execution / agent readiness | Coordinator behavior, blockers, human review | `order-execution` | Moved in pilot. |
| `wiki/order-execution/order-execution-state-model.md` | `order-execution` | Order execution | Quote-ready through relationship-ready state model | `order-execution` | Moved in pilot. |
| `wiki/order-execution/order-execution-transition-gate-rules.md` | `order-execution` | Order execution governance | Gate rules, blockers, warnings, overrides | `order-execution` | Moved in pilot because the gate rules are lane-specific. |
| `wiki/service/index.md` | `service` | Domain facet | Service/warranty/installed-base placeholder | Domain facet or `installed-base` later | Keep. |
| `wiki/current-state/index.md` | `current-state` | Current-state lane | Staff-validated operating truth | `current-state` | Keep quiet. |
| `wiki/governance/index.md` | `governance` | Governance facet | Review, source, freshness, conflict rules, evaluation discipline | `governance` | Keep. |
| `wiki/governance/source-manifest.md` | `governance` | Source governance | Source/provenance discipline | `governance` | Keep. |
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

This is a target proposal, not the active migration plan. The only piece of it active now is `order-execution`.

| Proposed folder | Role |
| --- | --- |
| `operating-model` | Parent lifecycle, role, value-stream, data-object, and distributor operating-model pages. |
| `workflows` | End-to-end lifecycle maps and cross-stage workflow pages that should not be owned by a department. |
| `lead-intelligence` | Source-aware lead intake, lead research, prospecting, target coverage, source quality, and outreach policy. |
| `quote-readiness` | Quote completeness, F&I readiness, proposal package readiness, pricing assumptions, approval provenance, and quote-source freshness. |
| `order-execution` | Closed-won through order readiness, vendor order, site readiness, delivery, install, closeout, and relationship-ready state. |
| `equipment` | Equipment ontology, manufacturer/model/source-freshness knowledge, and compatibility once upstream work matures. |
| `accounts-and-sites` | Account, property, site, contact, management company, buyer-path, and relationship-memory knowledge. |
| `installed-base` | Installed asset context, warranty, service history, replacement triggers, parts, and relationship expansion. |
| `agent-readiness` | Agent answerability, capability maps, context contracts, build bridges, fixture discipline, evaluation, and human-boundary patterns. |
| `governance` | Schema, review process, source manifests, freshness, conflict handling, provenance, and promotion/deprecation rules. |
| `knowledge-base` | Remaining wiki operating instructions and navigation patterns that do not yet belong in governance or agent-readiness. |
| `current-state` | Staff-validated actual Fit Supply operating notes, kept separate from target-state design. |

## Pilot Migration Result

The bounded pilot created `wiki/order-execution/` and moved these pages:

- `wiki/order-execution/close-won-to-delivery-workflow.md`.
- `wiki/order-execution/order-execution-readiness-agent-requirements.md`.
- `wiki/order-execution/order-execution-state-model.md`.
- `wiki/order-execution/order-execution-transition-gate-rules.md`.

The pilot intentionally did not move `wiki/governance/agent-evaluation-fixtures.md`, because that page governs fixture and trace discipline across future workflows. It also did not move `wiki/sales/freight-install-quote-readiness.md` or `wiki/sales/proposal-package-readiness.md`, because quote/proposal readiness is still a sales readiness lane without enough validated page density for a new folder.

## Migration Triggers

Do not move folders just because a term repeats. Move only when the current structure creates practical maintenance pain.

| Candidate Folder | Promote When |
| --- | --- |
| `wiki/order-execution/` | Already promoted as the first bounded pilot. Expand only with sourced post-close pages that belong in the same lane. |
| `wiki/lead-intelligence/` | Source-aware lead intake, lead research, hunter sales, source quality, and prospecting policy have multiple validated pages with repeated cross-links and shared ownership. |
| `wiki/agent-readiness/` or `wiki/agent-workflows/` | Multiple workflow pages become mature enough to need shared context contracts, build-readiness reviews, fixture/eval summaries, and human-boundary contracts. |
| `wiki/operating-model/` | Lifecycle, roles, data-object spine, value streams, and cross-domain maps outgrow `company` and `knowledge-base`. |
| `wiki/installed-base/` | Service, warranty, parts, replacement, asset lifecycle, and relationship-expansion pages become sourced enough to need a shared home. |
| `wiki/quote-readiness/`, `wiki/pricing-readiness/`, or `wiki/proposal-readiness/` | Freight/install, proposal package, tax, margin, financing, pricing source freshness, quote approval, and proposal-send review pages become validated enough that `sales` can no longer explain ownership, review, and source boundaries cleanly. |
| `wiki/accounts-and-sites/` | Account, property, site, contact, management-company, buyer-path, and relationship-memory pages become cross-cutting enough that `sales`, `projects`, and `service` all depend on them. |

## Proposed Future Shape

If the evidence keeps moving in the current direction, the likely future structure is not pure department folders. A better mature structure may look like:

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
  current-state/
```

This is a likely future shape, not the current migration plan.

The important idea is that `sales`, `projects`, and `service` may become lifecycle facets or page tags rather than the main organizing folders for every workflow page.

## What To Do Next

The bounded order-execution pilot migration is complete:

1. Use `wiki/order-execution/index.md` as the canonical home for post-close readiness, state, gate, delivery/install execution, and relationship-ready navigation.
2. Keep all other physical folders stable until new evidence justifies a separate promotion decision.
3. Keep `wiki/governance/agent-evaluation-fixtures.md` in governance.
4. Keep `wiki/sales/freight-install-quote-readiness.md` and `wiki/sales/proposal-package-readiness.md` in sales until quote/proposal readiness has broader validated page density.
5. Use `wiki/index.md` as the root lens path before browsing domain folders.
6. Use `wiki/knowledge-base/index.md` as the local hub for workflow, capability, structure, evaluation, and build-readiness lenses.
7. Use this page and [[domain-model-review|Domain Model Review]] before adding or moving any top-level folder.
8. When synthesizing the next non-gated roadmap family, repeat lifecycle, state/readiness, agent capability, evaluation/build-readiness, storage-domain fit, and domain-promotion classification before adding pages or moving folders.

## Decision

Promote `order-execution` as the first bounded workflow domain.

Do not run the full `v0.4` migration yet.

Do keep the operating rule:

```text
start from lifecycle, capability, and readiness maps
then land pages in the smallest structure that preserves meaning
and promote folders only when evidence creates real navigation pressure
```

This preserves simplicity while acknowledging Josh's concern: the starter folder structure is not the final answer. It is scaffolding while the better FAST OS-shaped information architecture emerges. The order-execution pilot lets the repo test that direction without making every immature lane look settled.