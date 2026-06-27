---
title: Agent Capability Map
type: Answerability-Target
domain: knowledge-base
knowledge_scope: target-state
status: Draft
last_reviewed:
reviewed_by:
sources:
  - raw/imports/fast-os-capability-roadmap-source-inventory.md#fscr-006
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/06-agent-workflow-decomposition/agent-candidate-inventory-v1.md
  - raw/imports/fast-os-capability-roadmap/regency-lead-to-closed-won-work-unit-decomposition-v1.md
  - raw/imports/fast-os-capability-roadmap/regency-close-won-to-delivery-workflow-decomposition-v1.md
  - wiki/sales/source-aware-lead-intake-routing.md
  - wiki/sales/freight-install-quote-readiness.md
  - wiki/order-execution/index.md
related:
  - [[distributor-workflow-map|Distributor Workflow Map]]
  - [[../company/commercial-fitness-distributor-operating-model|Commercial Fitness Distributor Operating Model]]
  - [[../sales/source-aware-lead-intake-routing|Source-Aware Lead Intake And Routing]]
  - [[../sales/lead-to-closed-won-workflow|Lead To Closed Won Workflow]]
  - [[../sales/freight-install-quote-readiness|Freight And Install Quote Readiness]]
  - [[../order-execution/index|Order Execution]]
  - [[../order-execution/close-won-to-delivery-workflow|Close Won To Delivery Workflow]]
  - [[agent-answerability-targets|Agent Answerability Targets]]
agent_answerability:
  - Which agent capability clusters should the wiki support before productized agents are named?
  - What human review boundaries should apply across sales, design, project, service, and governance workflows?
  - Which schema families recur across workflow stages?
tags:
  - agent-capabilities
  - answerability
  - roadmap-derived
provenance_notes: Synthesized from FSCR-006. Cluster names are candidate capability boundaries, not final product agent names. Updated 2026-06-27 after order-execution became the first promoted workflow domain.
---

# Agent Capability Map

This page translates the roadmap agent candidate inventory into an LLM Wiki answerability map.

The clusters below are not final agent names. They are capability boundaries that repeat across cases and share context, outputs, risk, review needs, workflow signals, and schema families.

## Current Cluster Summary

| ID | Capability Cluster | Lifecycle Span | Evidence Strength | Target AI Posture | Human Boundary |
| --- | --- | --- | --- | --- | --- |
| ACI-01 | Source intelligence | Lead identification / qualification | Strong | Observe, classify, preserve provenance, dedupe, and recommend route. | Human confirms ambiguous ownership, route, or customer-facing action. |
| ACI-02 | Research and enrichment | Qualification / discovery | Medium | Prepare research brief and recommendation. | Human chooses pursue, park, reject, monitor, assign, or outreach. |
| ACI-03 | Inbound quote-readiness | Qualification / quote prep | Medium | Detect bid intent, extract request, identify missing quote inputs, and prepare response path. | Rep approves customer-facing quote or clarification. |
| ACI-04 | Site-visit capture and debrief | Discovery / site survey | Strong | Guide capture, extract context, ask debrief questions, and prepare reviewed summary. | Rep confirms facts before downstream design, quote, or handoff use. |
| ACI-05 | Project-context readiness | Site survey / design / quote / handoff | Strong | Assemble structured context and blocker checks. | Humans validate sensitive commercial facts and readiness blockers. |
| ACI-06 | Solution design support | Layout / equipment selection | Medium | Recommend options with rationale and assumptions. | Rep owns final product, layout, and customer recommendation. |
| ACI-07 | Quote and proposal readiness | Pricing / quote / proposal | Strong | Prepare package, checklist, assets, draft message, and freight/install readiness packet. | Rep approves customer-facing price, scope, F&I values, and promise. |
| ACI-08 | Follow-up and decision-state | Follow-up / objection / close | Strong | Track state, draft reminders, detect stalls, and suggest purposeful next touch. | Rep owns relationship-sensitive pressure, tone, and outcome reason. |
| ACI-09 | Approval and handoff readiness | Close / procurement boundary | Strong | Detect approval, compare terms, prepare handoff packet, and surface gaps. | Human confirms commitment, commercial/legal mismatch, and handoff release. |
| ACI-10 | Order coordination | Procurement / vendor / payment | Medium | Track vendor/payment/shipment status and prepare packets or updates. | Accounting, purchasing, PM, or sales approves financial, vendor, and customer commitments. |
| ACI-11 | Install readiness | Delivery / install prep | Medium | Assemble site, equipment, layout, receiving, and delivery readiness context. | PM/installer validates release and scheduling. |
| ACI-12 | Completion and relationship continuity | Install completion / relationship expansion | Medium | Capture completion proof, organize exceptions, and trigger follow-up. | Humans validate exceptions, warranty-impacting claims, and relationship cadence. |
| ACI-13 | Playbook governance | Cross-stage learning | Early | Propose reusable workflow patterns after repeated evidence. | Human/product review approves versioning, reuse, correction, and retirement. |

## Strongest Near-Term Candidates

The roadmap inventory identifies these as the strongest early clusters because they connect directly to a sales-first FAST OS strategy and produce context later operations need:

1. Source intelligence.
2. Inbound quote-readiness.
3. Quote and proposal readiness.
4. Follow-up and decision-state.
5. Site-visit capture and debrief.
6. Approval and handoff readiness.

Order coordination, install readiness, completion, service, warranty, and relationship expansion matter, but they depend on clean upstream quote, approval, site, and handoff context. Building those downstream workflows before the upstream model is stable would create false progress.

## Current Source-Aware Lead Intake Lane

[[../sales/source-aware-lead-intake-routing|Source-Aware Lead Intake And Routing]] is now the compiled wiki home for ACI-01 source intelligence and the intake-side boundary between ACI-02 research/enrichment and ACI-03 inbound quote-readiness.

The practical rule for future agents is: classify the source event and quote-readiness distance before choosing the first output. A service-created replacement signal, owner-forwarded project-intelligence item, inbound bid request, and formal project-intelligence feed should not all receive the same lead brief, research depth, or quote-prep treatment.

## Current Freight And Install Quote-Readiness Lane

[[../sales/freight-install-quote-readiness|Freight And Install Quote Readiness]] is now the compiled wiki home for the F&I portion of ACI-07 quote and proposal readiness, with connections to ACI-05 project-context readiness, ACI-09 approval and handoff readiness, ACI-10 order coordination, and ACI-11 install readiness.

The practical rule for future agents is: prepare freight/install/extraction readiness, estimates, exception routes, provenance, validity, and handoff assumptions, but require human approval before any customer-facing financial value or quote resend.

## Boundary Rules

| Boundary | Rule |
| --- | --- |
| Source intelligence vs research/enrichment | Route by source type, quote-readiness distance, account context, and missing facts. Do not research every lead by default. |
| Research/enrichment vs pursuit planning | Research decides whether and why something is worth action. Pursuit planning designs the action path. |
| Site capture vs project-context readiness | Capture gathers facts. Readiness decides whether the facts are complete enough for a downstream decision. |
| Solution design vs quote/proposal readiness | Design and product fit are judgment-heavy. Proposal assembly may be partly mechanical but remains financially and trust sensitive. |
| Follow-up state vs relationship action | AI can track, remind, and draft. Humans own relationship pressure and customer-sensitive decisions. |
| Closed-won vs order-ready | Approval is not executable readiness. The wiki should keep these as separate states. |
| Site-ready vs delivery-ready | Site survey completeness is not the same as release readiness for installer or delivery team. |
| Install-complete vs relationship-ready | Completion evidence must be reviewed before relationship, installed-base, and service workflows treat the project as complete. |

## Minimum Schema Families

| Cluster | Minimum Object / Event Families |
| --- | --- |
| Source intelligence | `SourceEvent`, `LeadSignal`, `LeadRouteDecision`, `LeadCurationEvent`, `SourceOutcome`, `SourceQualitySignal` |
| Research and enrichment | `ResearchRun`, `LeadResearchBrief`, `ResearchReviewEvent`, `ResearchOutcome`, `AmenityRelevanceSignal`, `BuyerPathHypothesis` |
| Inbound quote-readiness | `InboundLeadSignal`, `RequestedProduct`, `ProductAlias`, `SKUCandidate`, `MissingContextQuestion`, `QuoteReadinessChecklist` |
| Site-visit capture and debrief | `SiteVisitEvent`, `SiteVisitSummary`, `RoomContext`, `MeasurementSet`, `PhotoSet`, `ProcurementContext` |
| Project-context readiness | `ProjectContextPacket`, `QuoteBlocker`, `OrderBlocker`, `ExtractionInstruction`, `FlooringScope`, `TradeInPacket` |
| Solution design support | `LayoutPlan`, `ProductSelectionRationale`, `ProductOptionSet`, `ProposalPositioningNote` |
| Quote and proposal readiness | `Quote`, `QuoteVersion`, `PriceFreshnessCheck`, `QuoteReadinessChecklist`, `FreightInstallInputPacket`, `FreightEstimate`, `FreightEstimateMode`, `FreightValidityWindow`, `InstallEstimate`, `ExtractionLine`, `EstimateReviewEvent`, `ProposalPackage`, `ProposalDeliveryEvent` |
| Follow-up and decision-state | `FollowUpState`, `FollowUpTask`, `BidCollectionStatus`, `Interaction`, `ConversionStatus`, `WinLossReason` |
| Approval and handoff readiness | `ApprovalProof`, `PurchaseOrderReview`, `ContractReviewHighlight`, `CustomerCommitmentEvent`, `ClosedWonEvent`, `OrderReadinessState`, `OrderReadinessChecklist`, `OrderHandoffReviewEvent` |
| Order coordination | `InvoiceMilestonePlan`, `VendorPurchaseOrder`, `VendorAcknowledgmentEvent`, `LeadTimeStatus`, `ReceivingEvent`, `CustomerStatusUpdateEvent` |
| Install readiness | `SiteSurvey`, `SiteReadinessStatus`, `DeliveryReadinessState`, `ReadinessExport`, `ApprovedLayoutArtifact`, `InstallScheduleEvent` |
| Completion and relationship continuity | `InstallationCompletionPacket`, `DeliveryConfirmation`, `PunchListItem`, `InstalledAsset`, `RelationshipFollowUpPlan` |
| Playbook governance | `WorkflowPlaybook`, `PlaybookVersion`, `TriggerRule`, `OutputTemplate`, `GovernanceStatus`, `PlaybookReviewEvent` |

## UI And Interaction Principle

Future agent surfaces should be workflow-centered, not a list of named agents.

```text
show the work unit, the decision, the evidence, the missing facts, and the next state change
```

Likely early surfaces include a source review queue, research brief workspace, site-visit capture/debrief, quote readiness workspace, follow-up state view, handoff packet workspace, and delivery readiness workspace.

## Validation Needs

- Validate lead source priority and frequency before hard-coding source-intelligence routes.
- Validate Josh's actual research steps before productizing research/enrichment.
- Define minimum quote-readiness and order-readiness blockers versus warnings, including freight/install/extraction blockers and review thresholds.
- Unpack product-fit rationale across more cases before making recommendation logic feel objective.
- Define follow-up states that support the rep without creating shame or busywork.
- Validate handoff ownership across sales, project management, accounting, purchasing, and order teams.
- Treat commercial equipment catalog/schema answerability as upstream-owned by `fast-os-knowledge-base` until mature enough to consume here.
