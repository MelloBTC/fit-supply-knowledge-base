---
title: Distributor Workflow Map
type: Process
domain: knowledge-base
knowledge_scope: target-state
status: Draft
last_reviewed:
reviewed_by:
sources:
  - raw/imports/fast-os-capability-roadmap-source-inventory.md#fscr-003
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/06-agent-workflow-decomposition/macro-workflow-map-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/05-capability-roadmap/commercial-fitness-dealer-operating-model-v1.md
  - wiki/sales/source-aware-lead-intake-routing.md
  - wiki/sales/freight-install-quote-readiness.md
  - wiki/sales/proposal-package-readiness.md
  - wiki/order-execution/index.md
related:
  - [[../company/commercial-fitness-distributor-operating-model|Commercial Fitness Distributor Operating Model]]
  - [[agent-capability-map|Agent Capability Map]]
  - [[../sales/source-aware-lead-intake-routing|Source-Aware Lead Intake And Routing]]
  - [[../sales/lead-to-closed-won-workflow|Lead To Closed Won Workflow]]
  - [[../sales/freight-install-quote-readiness|Freight And Install Quote Readiness]]
  - [[../sales/proposal-package-readiness|Proposal Package Readiness]]
  - [[../order-execution/close-won-to-delivery-workflow|Close Won To Delivery Workflow]]
  - [[roadmap-import-plan|Roadmap Import Plan]]
agent_answerability:
  - Which lifecycle stage does a workflow, source artifact, or agent candidate belong to?
  - What compiled wiki page should an agent read for a cross-domain distributor workflow question?
  - Which workflow stages are strong enough for synthesis, and which remain deferred or upstream-owned?
tags:
  - workflow-map
  - lifecycle
  - roadmap-derived
provenance_notes: Synthesized from FSCR-003 as a wiki navigation layer, not copied as the full roadmap artifact table of contents. Updated 2026-06-27 after the proposal package readiness synthesis and bounded order-execution pilot migration.
---

# Distributor Workflow Map

This page is the compiled lifecycle map for the target-state distributor wiki. It translates the roadmap macro workflow into a navigable LLM Wiki view.

Use it before creating a new workflow page. The goal is to prevent duplicate pages, disconnected workflow slices, and premature agent naming.

## Macro Lifecycle

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

Real workflows can loop backward. Site survey can change qualification, layout can change equipment selection, and quote revision can trigger new discovery.

## Lifecycle Map

| Stage | Business Question | Current Wiki Home | Synthesis Status | Notes |
| --- | --- | --- | --- | --- |
| Lead Identification | Where does possible demand come from? | `sales`, `knowledge-base` | Synthesized in [[../sales/source-aware-lead-intake-routing|Source-Aware Lead Intake And Routing]]. | Lead-source type, provenance, first route, owner, and outcome state now have a compiled wiki home. |
| Qualification | Is the lead worth action, and what route should it take? | `sales` | Covered at source-routing level in [[../sales/source-aware-lead-intake-routing|Source-Aware Lead Intake And Routing]] and downstream in [[../sales/lead-to-closed-won-workflow|Lead To Closed Won Workflow]]. | Research/enrichment remains source-backed but needs validation against more actual dealer steps. |
| Discovery | Is this a real project, who is involved, and what needs to be learned? | `sales`, `company` | Case-backed through Regency lead-to-closed-won. | More cases should refine buyer and discovery decision inventories. |
| Site Survey | What must be captured about the space before design, quote, delivery, and install? | `design`, `projects` | Strong evidence from Regency, but field thresholds need validation. | Site capture should feed design, quote, handoff, and install readiness. |
| Layout and Design | How does room context become a usable layout and design direction? | `design` | Strong case signal, not yet a standalone design workflow page. | Create a design workflow page only when layout/design decomposition needs its own canonical home. |
| Equipment Selection | What mix fits the room, property, budget posture, customer goals, and distributor strategy? | `equipment`, `sales`, `design` | Synthesis should wait for upstream commercial equipment knowledge maturity. | Product/catalog answerability remains owned by `fast-os-knowledge-base` for now. |
| Pricing and Quote Creation | Can the offer be priced accurately, profitably, and with correct freight/install assumptions? | `sales`, `governance` | Freight/install quote readiness is now synthesized in [[../sales/freight-install-quote-readiness|Freight And Install Quote Readiness]]; full quote/pricing policy remains deferred. | Avoid confident product/pricing claims without source/freshness controls; customer-facing F&I values require review. |
| Proposal Assembly | How does the quote become a persuasive, reviewed customer-facing package? | `sales`, `design`, `projects` | Synthesized in [[../sales/proposal-package-readiness|Proposal Package Readiness]] and covered at a case-backed level in [[../sales/lead-to-closed-won-workflow|Lead To Closed Won Workflow]]. | Keep proposal package readiness in sales; do not turn it into autonomous proposal generation or a new domain yet. |
| Follow-Up and Objection Handling | What happens after the proposal is sent, and how does the system prevent silent stalls? | `sales` | Covered in lead-to-closed-won and agent capability map. | Follow-up state should distinguish bid collection from no response. |
| Close and Procurement | What proves the customer commitment, and what must be complete before operations acts? | `sales`, `order-execution` | Strong boundary established. | Closed-won and order-ready must remain separate states. |
| Delivery and Install | How does equipment get received, scheduled, installed, accepted, and documented? | `order-execution`, `service` | Covered in [[../order-execution/index|Order Execution]] through the close-won workflow, readiness requirements, state model, and transition gate rules. | Evaluation fixture discipline remains in governance. |
| Service and Warranty | How does installed equipment become serviceable account knowledge? | `service`, `equipment` | Parent model only. | Defer deep service/warranty detail until a real case or upstream source work supports it. |
| Relationship Expansion | How does completed work create repeat revenue and future demand? | `sales`, `service`, `company` | Strategic direction only. | Needs account lifecycle trigger cases before durable rules are created. |

## High-Value Boundaries

| Boundary | Why It Matters | Current Read |
| --- | --- | --- |
| Source intelligence vs research/enrichment | Not every lead deserves research; source type and quote-readiness distance should decide route. | Strong. [[../sales/source-aware-lead-intake-routing|Source-Aware Lead Intake And Routing]] now preserves this as the compiled intake rule. |
| Site capture vs project-context readiness | Capture is how facts enter the system; readiness decides whether downstream work has enough validated context. | Strong. Regency shows both are needed. |
| Solution design vs quote/proposal readiness | Product/layout judgment is different from customer-facing package assembly. | Strong. The rep owns the recommendation and customer-facing approval. |
| Project-context ready vs proposal-ready | Having site notes or design assets is not the same as having a reviewed customer-facing package. | Strong. [[../sales/proposal-package-readiness|Proposal Package Readiness]] now owns the compiled package-readiness lane. |
| Freight/install estimate vs quote-ready | A freight, install, or extraction number is not enough; source, assumptions, confidence, validity, reviewer, and quote version must be preserved before customer-facing use. | Strong. [[../sales/freight-install-quote-readiness|Freight And Install Quote Readiness]] now owns the compiled F&I readiness lane. |
| Follow-up state vs relationship action | The system can prevent silent stalls, but the rep owns tone, pressure, and relationship judgment. | Strong. Park and Regency both show follow-up leakage or ambiguity. |
| Closed-won vs order-ready | Closed-won proves commitment; order-ready proves executable handoff. | Strong. This is a core anti-false-progress boundary. |
| Site-ready vs delivery-ready | Site survey completeness is not the same as installer release readiness. | Strong inference. Needs field threshold validation. |
| Install-complete vs relationship-ready | Completion evidence should trigger relationship management and installed-base context. | Medium. Needs post-install cases. |

## Cross-Stage Foundations

- Workflow decomposition method: keep workflow pages agent-ready by naming outcome, work units, decisions, context, outputs, risk, autonomy, and schema implications.
- Repo data boundaries: raw customer evidence should not enter Git unless intentionally sanitized and imported.
- Source preservation: case-backed pages should cite raw imports or roadmap source paths, not just summaries.
- Open question control: unresolved validation needs should remain visible rather than smoothed into target-state truth.
- Agent candidate inventory: use capability clusters before naming productized agents.
- Product/build bridge: defer implementation requirements until wiki pages and answerability targets are stable enough.

## Recommended Wiki Build Sequence

1. Use [[../company/commercial-fitness-distributor-operating-model|Commercial Fitness Distributor Operating Model]] as the parent lifecycle map.
2. Use this page as the cross-domain workflow navigation layer.
3. Use [[agent-capability-map|Agent Capability Map]] to keep AI support framed as capability clusters, not premature product agents.
4. Use [[../sales/source-aware-lead-intake-routing|Source-Aware Lead Intake And Routing]] to classify lead signals before routing into quote readiness, research/enrichment, pursuit planning, or follow-up.
5. Use [[../sales/freight-install-quote-readiness|Freight And Install Quote Readiness]] when quote completeness depends on freight, install, extraction, review/provenance, or downstream handoff assumptions.
6. Use [[../sales/proposal-package-readiness|Proposal Package Readiness]] when customer-facing package readiness depends on project context, room uncertainty, design assets, visual review, quote/package alignment, delivery event, or follow-up state.
7. Use [[../sales/lead-to-closed-won-workflow|Lead To Closed Won Workflow]] and [[../order-execution/close-won-to-delivery-workflow|Close Won To Delivery Workflow]] as the first case-backed workflow pages.
8. Defer deep equipment/catalog answerability until `fast-os-knowledge-base` has mature outputs to evaluate.
9. Use [[../order-execution/index|Order Execution]] for post-close readiness, state-transition, gate-rule, delivery/install, completion, and relationship-ready navigation; do not extend the broader folder migration without new evidence and approval.
