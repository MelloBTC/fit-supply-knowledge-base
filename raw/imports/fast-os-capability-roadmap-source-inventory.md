# FAST OS Capability Roadmap Source Inventory

Generated: 2026-06-27
Source repo: `C:\Users\joshm\projects\fast-os-capability-roadmap`
Inventory mode: read-only source discovery

## Purpose

This inventory identifies roadmap artifacts that may become source material, compiled wiki pages, answerability targets, governance patterns, or future domain additions for the target-state Fit Supply Knowledge Base.

This file does not import the source artifacts themselves. It records candidate use before any copy or synthesis step.

## Classification Legend

- `target-state`: designed future-state operating model or knowledge structure.
- `reference-pattern`: reusable distributor pattern informed by Fit Supply examples.
- `design-hypothesis`: plausible but not yet validated pattern.
- `current-state`: actual Fit Supply current operations.

## Candidate Artifact Inventory

| ID | Source path | Summary | Recommended domain | Knowledge scope | Candidate wiki destination | Answerability supported | Sensitivity / review concerns | Import recommendation | Domain model notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| FSCR-001 | `docs/06-agent-workflow-decomposition/README.md` | Navigation surface for workflow decomposition artifacts and active/proposed near-term files. | `knowledge-base` | `reference-pattern` | `wiki/knowledge-base/roadmap-import-plan.md` | Helps agents understand which roadmap files matter and how work-unit catalogs relate. | Contains roadmap-specific references; should be summarized, not copied wholesale. | `governance-pattern` | Confirms this inventory should start in `docs/06-agent-workflow-decomposition/`. |
| FSCR-002 | `docs/05-capability-roadmap/commercial-fitness-dealer-operating-model-v1.md` | Target-state dealer lifecycle, role map, value-stream decomposition, data object spine, and validation needs. | `knowledge-base`, `company` | `target-state` | `wiki/company/commercial-fitness-distributor-operating-model.md` | What is the end-to-end operating model for an agent-ready commercial fitness distributor? | Some sections need Josh/Fit Supply validation; should not be treated as current-state. | `synthesize-wiki` | May justify new `operating-model` or `workflow-model` domain after review. |
| FSCR-003 | `docs/06-agent-workflow-decomposition/macro-workflow-map-v1.md` | Macro lifecycle map across lead identification, qualification, discovery, site survey, design, equipment selection, quoting, close, delivery/install, service, and relationship expansion. | `knowledge-base`, `projects` | `target-state` | `wiki/knowledge-base/distributor-workflow-map.md` | What lifecycle stages should the wiki and future agents cover? | Large artifact with many roadmap links; import as structured map, not direct copy. | `synthesize-wiki` | Strong evidence the starter domains may expand into lifecycle or agent-workflow views. |
| FSCR-004 | `docs/06-agent-workflow-decomposition/fast-os-commercial-equipment-knowledge-layer-options-memo-2026-06-20.md` | Catalog/schema risk, equipment answerability, source manifest pattern, validation gates, and repo-boundary options for commercial equipment knowledge. | `equipment`, `governance`, `knowledge-base` | `target-state` | Deferred; future adaptation from `fast-os-knowledge-base` when mature | What equipment questions can agents answer, what evidence is required, and when should they refuse/escalate? | Active work now belongs in `fast-os-knowledge-base`; do not duplicate in this repo. | `upstream-dependency` | Track as a boundary reference only; revisit after upstream maturity. |
| FSCR-005 | `docs/06-agent-workflow-decomposition/fast-os-knowledge-layer-planning-checkpoint-2026-06-20.md` | Cross-repo knowledge-layer planning checkpoint around catalog/schema risk, answerability, provenance, validation gates, and next sequence. | `governance`, `knowledge-base` | `reference-pattern` | `wiki/knowledge-base/knowledge-layer-planning-checkpoint.md` | What sequence should this knowledge base follow before implementation or live retrieval? | Checkpoint may include repo-boundary context not needed in compiled pages. | `answerability-target` | Useful as planning context; likely not first compiled domain page. |
| FSCR-006 | `docs/06-agent-workflow-decomposition/agent-candidate-inventory-v1.md` | Cross-case candidate agent clusters from source intelligence through relationship continuity, with work-unit patterns, schema families, UI implications, and open questions. | `knowledge-base`, `sales`, `projects`, `service` | `target-state` | `wiki/knowledge-base/agent-capability-map.md`; domain-specific agent pages | Which agent clusters should exist and what human boundaries should they respect? | Cluster names are candidate-level, not final product names. | `synthesize-wiki` | May justify new `agent-workflows` domain. |
| FSCR-007 | `docs/06-agent-workflow-decomposition/regency-lead-to-closed-won-work-unit-decomposition-v1.md` | Work-unit decomposition from outbound campaign response through site visit, layout, product selection, quote/proposal, follow-up, approval, closed-won, and order-readiness boundary. | `sales`, `design`, `equipment`, `projects` | `target-state` | `wiki/sales/lead-to-closed-won-workflow.md` | What must happen between lead signal and closed-won before operations can safely act? | Contains case-specific dates and current evidence labels; preserve provenance and avoid overgeneralizing. | `import-raw` then `synthesize-wiki` | Strong pilot candidate for first sales/design/equipment workflow page. |
| FSCR-008 | `docs/06-agent-workflow-decomposition/regency-close-won-to-delivery-workflow-decomposition-v1.md` | Post-close workflow from approval proof through order readiness, vendor POs, payment, site survey, delivery/install readiness, completion evidence, and relationship transition. | `projects`, `service`, `current-state` | `target-state` | `wiki/projects/close-won-to-delivery-workflow.md` | What separates closed-won from order-ready, delivery-ready, install-complete, and relationship-ready? | Explicitly includes current Fit Supply/NetSuite as current-state evidence only. | `import-raw` then `synthesize-wiki` | May justify a dedicated `order-execution` domain. |
| FSCR-009 | `docs/06-agent-workflow-decomposition/order-execution-readiness-agent-requirements-v1.md` | Build-facing agent requirements for readiness gates, human review boundaries, rep visibility, data objects, UI controls, fixtures, evals, and observability. | `projects`, `knowledge-base`, `governance` | `target-state` | `wiki/projects/order-execution-readiness-agent-requirements.md`; `wiki/governance/human-review-boundaries.md` | What should an order/execution readiness agent detect, classify, route, draft, preserve, monitor, recommend, and record? | Implementation-adjacent; should be translated into wiki patterns, not treated as code spec. | `synthesize-wiki` | Strong reason to consider `order-execution` as a future domain. |
| FSCR-010 | `docs/06-agent-workflow-decomposition/order-execution-state-transition-model-v1.md` and `order-execution-transition-gate-rules-v1.md` | State ladder and gate rules for quote-ready through relationship-ready, including blockers, warnings, owners, evidence, overrides, and agent actions. | `projects`, `governance` | `target-state` | `wiki/projects/order-execution-state-model.md`; `wiki/governance/transition-gate-rules.md` | What state transitions should future agents evaluate, and what evidence blocks or warns? | Needs careful synthesis because exact thresholds may be dealer-specific. | `synthesize-wiki` | Supports validation-gate and workflow-state modeling. |
| FSCR-011 | `docs/06-agent-workflow-decomposition/order-execution-gate-evaluation-checklist-and-eval-spec-v1.md`, `order-execution-gate-evaluation-synthetic-test-suite-v1.md`, and `../../fixtures/order-execution-gate-evaluation-v1/README.md` | Synthetic evaluation suite and fixture bundle for order/execution readiness gates. | `governance`, `projects` | `target-state` | `wiki/governance/agent-evaluation-fixtures.md` | How can readiness agents be tested before real customer data is loaded? | Machine-readable fixtures should remain upstream unless intentionally imported later. | `answerability-target` | Useful for future eval discipline; not first content synthesis unless testing becomes active. |
| FSCR-012 | `docs/06-agent-workflow-decomposition/hunter-sales-*.md` and `../../fixtures/hunter-sales-existing-multifamily-policy-evaluator-v1/README.md` | Existing multifamily hunter-sales policy validation, evaluator specs, synthetic/provisional scenarios, and validation labels. | `sales`, `governance` | `design-hypothesis` | `wiki/sales/hunter-sales-existing-multifamily-pattern.md` | How should a sales/prospecting agent treat target accounts, budget windows, no-response cases, manager changes, hard stops, and sensitive accounts? | Many scenarios are provisional; keep validation labels intact. | `defer` for first pass; later `synthesize-wiki` | May justify `lead-intelligence` or `prospecting` domain after roadmap review. |
| FSCR-013 | `docs/06-agent-workflow-decomposition/agent-build-bridge-to-product-roadmap-v1.md` | Bridge from workflow decomposition to product data, schema, fixtures, evaluation, and implementation requirements. | `knowledge-base`, `governance` | `reference-pattern` | `wiki/knowledge-base/wiki-to-agent-build-bridge.md` | How should wiki knowledge eventually become build-ready agent requirements? | Product-specific details need adaptation. | `governance-pattern` | Useful later when moving from wiki design to implementation planning. |
| FSCR-014 | `docs/06-agent-workflow-decomposition/agent-architecture-exploration-v1.md` | Non-final architecture exploration for workflow orchestration, capability workers, evaluator services, state, tools, human review, and observability. | `knowledge-base`, `governance` | `reference-pattern` | `wiki/knowledge-base/agent-architecture-patterns.md` | What architectural components may be needed once the knowledge base powers agents? | Exploratory and non-final; avoid overfitting current wiki to this architecture. | `defer` | Keep as future architecture reference, not near-term wiki content. |
| FSCR-015 | `docs/05-capability-roadmap/*case-study*.md` including Park, TSU, Lenox, Bailey, and Regency case studies | Case-specific examples feeding source intelligence, research/enrichment, inbound quote-readiness, service-created replacement signals, and proposal/order workflows. | `sales`, `service`, `projects`, `current-state` | `target-state` | domain-specific case-backed pages after source review | Which examples validate agent workflow patterns and which remain hypotheses? | Must preserve evidence labels and avoid exposing sensitive customer details if shared externally. | `import-raw` selectively after reviewing each case | Strong support for future pilot pages; should not be bulk-imported. |

## Initial Domain Expansion Signals

The starter skeleton is useful but incomplete. The roadmap inventory suggests these possible future domains or cross-domain lenses:

| Candidate domain/lens | Why it may be needed | Decision status |
| --- | --- | --- |
| `agent-workflows` | Agent candidate clusters cut across sales, design, projects, service, and governance. | Keep as a `knowledge-base` answerability lens for now; revisit after multiple agent-workflow contract pages exist. |
| `operating-model` | The dealer lifecycle and data object spine may deserve a stable home outside `company`. | Keep as a canonical page in `company` for now; revisit if lifecycle, value-stream, role, and data-object pages multiply. |
| `order-execution` | Close-won, order readiness, vendor ordering, site readiness, delivery, install, completion, and relationship-ready are dense enough to outgrow `projects`. | Promote as the next synthesis lane inside `projects` and `governance`; create a top-level domain only after compiled page density justifies it. |
| `lead-intelligence` or `prospecting` | Hunter sales and source intelligence have their own policies, fixtures, and validation labels. | Defer as a `sales` sub-lane until target-state sales workflow pages and validation labels are stronger. |
| `installed-base` | Service, warranty, lifecycle, replacement, and relationship expansion may need a durable domain later. | Defer as a service/equipment lifecycle lens until service, warranty, or replacement pages are sourced. |

## Original Recommended First Import Slice

1. Synthesize FSCR-002 and FSCR-003 into an operating model and macro workflow map.
2. Synthesize FSCR-006 into an agent capability map and use it to refine answerability targets.
3. Import raw copies of FSCR-007 and FSCR-008 only when ready to build the first case-backed workflow pages.
4. Keep FSCR-004 as an `upstream-dependency` owned by `fast-os-knowledge-base`; revisit only after that repo's work is mature enough to evaluate for inclusion.

## Initial Synthesis Progress

Completed on 2026-06-27:

| ID | Result |
| --- | --- |
| FSCR-002 | Synthesized into `wiki/company/commercial-fitness-distributor-operating-model.md`. |
| FSCR-003 | Synthesized into `wiki/knowledge-base/distributor-workflow-map.md`. |
| FSCR-006 | Synthesized into `wiki/knowledge-base/agent-capability-map.md`. |
| FSCR-007 | Imported to `raw/imports/fast-os-capability-roadmap/regency-lead-to-closed-won-work-unit-decomposition-v1.md` and synthesized into `wiki/sales/lead-to-closed-won-workflow.md`. |
| FSCR-008 | Imported to `raw/imports/fast-os-capability-roadmap/regency-close-won-to-delivery-workflow-decomposition-v1.md` and synthesized into `wiki/projects/close-won-to-delivery-workflow.md`. |
| FSCR-004 | Preserved as an upstream dependency owned by `fast-os-knowledge-base`; not locally synthesized. |

## What Not To Do Yet

- Do not bulk-copy every roadmap artifact into `raw/`.
- Do not promote hunter-sales provisional scenarios into target-state rules without preserving validation labels.
- Do not let current Fit Supply/NetSuite process details dominate the target-state model.
- Do not add implementation architecture pages before answerability and source contracts are clearer.
- Do not replicate active `fast-os-knowledge-base` catalog/schema risk, equipment answerability, source manifest, validation gate, or repo-boundary work.
