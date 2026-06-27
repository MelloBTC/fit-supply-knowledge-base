---
title: Lead To Closed Won Workflow
type: Workflow
domain: sales
knowledge_scope: target-state
status: Draft
last_reviewed:
reviewed_by:
sources:
  - raw/imports/fast-os-capability-roadmap-source-inventory.md#fscr-007
  - raw/imports/fast-os-capability-roadmap/regency-lead-to-closed-won-work-unit-decomposition-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/06-agent-workflow-decomposition/regency-lead-to-closed-won-work-unit-decomposition-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/05-capability-roadmap/regency-proposal-workflow-cross-repo-synthesis-v1.md
  - wiki/sales/proposal-package-readiness.md
related:
  - [[../knowledge-base/distributor-workflow-map|Distributor Workflow Map]]
  - [[../knowledge-base/agent-capability-map|Agent Capability Map]]
  - [[../company/commercial-fitness-distributor-operating-model|Commercial Fitness Distributor Operating Model]]
  - [[../order-execution/close-won-to-delivery-workflow|Close Won To Delivery Workflow]]
  - [[freight-install-quote-readiness|Freight And Install Quote Readiness]]
  - [[proposal-package-readiness|Proposal Package Readiness]]
agent_answerability:
  - What must happen between a campaign response or lead signal and closed-won before operations can safely act?
  - Which context must be captured before quote/proposal work becomes trustworthy?
  - Which sales workflow actions can AI prepare, and which require rep review?
tags:
  - sales-workflow
  - case-backed
  - regency
  - roadmap-derived
provenance_notes: Synthesized from sanitized Regency roadmap artifact FSCR-007. Case facts are evidence-backed where the source labels them as such; this page generalizes them into a target-state workflow. Updated 2026-06-27 to link FSCR-018 proposal package readiness as the deeper proposal assembly lens.
---

# Lead To Closed Won Workflow

This page captures the target-state workflow from a qualified lead signal through approved quote and closed-won. The first case-backed source is the Regency at Dell Ranch workflow, which began as an outbound campaign response and ended at the order-readiness boundary.

This is not the post-close delivery workflow. Post-close work continues in [[../order-execution/close-won-to-delivery-workflow|Close Won To Delivery Workflow]].

## Business Outcome

Turn a customer response or lead signal into a scoped, designed, quoted, approved, and handoff-ready won project.

```text
customer expresses replacement or project need
-> lead signal is preserved and routed
-> site/project context is captured
-> layout and product rationale support quote/proposal
-> customer-facing proposal is reviewed and sent
-> follow-up state is tracked
-> approval proof is captured
-> closed-won is prepared for order-readiness review
```

## Source Boundary

The Regency source artifact is sanitized. It does not copy raw customer emails, quote PDFs, pricing details, signatures, photos, dimensions, or private project files into this repo. This page preserves the synthesized workflow pattern and cites the imported source copy under `raw/imports/`.

## Workflow Spine

| Stage | Target-State State Change | Case-Backed Signal |
| --- | --- | --- |
| Campaign response or lead signal | Response becomes a source-backed `LeadSignal`, not just an email in memory. | Regency began with an outbound campaign-style response. |
| Qualification and route | Rep confirms whether the lead deserves site visit, quote prep, research, park, reject, or monitor. | The customer asked for replacement quote help and needed a site visit. |
| Discovery and site visit | Physical room and project context become reusable structured context. | Measurements, photos, notes, flooring, trade-in, and procurement context mattered. |
| Layout and product selection | Layout direction and product-selection rationale become quote input. | Layout came before final equipment selection. |
| Quote/proposal readiness | Freight/install, trade-in, flooring, terms, specs, room/design assets, visuals, and proposal package are checked before send. | QTE35768, F&I, trade-in, and proposal delivery were part of the case; F&I readiness now lives in [[freight-install-quote-readiness|Freight And Install Quote Readiness]], while proposal package readiness now lives in [[proposal-package-readiness|Proposal Package Readiness]]. |
| Follow-up and bid state | Waiting is made explicit as bid collection, no response, stalled, revision requested, won, lost, or parked. | Regency entered a three-bid collection state. |
| Approval and closed-won | Approval proof and accepted quote version are confirmed before closing sales workflow. | Approved quote received and quote converted to closed won. |
| Order-readiness boundary | Sales context is packaged for post-close review. | Source artifact treats closed-won as the start of order readiness, not as automatic execution readiness. |

## Work Unit Groups

| Group | Source Work Units | Recurring Decision | Required Context | Output / State | AI Posture | Human Boundary |
| --- | --- | --- | --- | --- | --- | --- |
| Source and relationship preservation | LCW-01 to LCW-03 | What produced the lead, and how should related properties be linked without merging outcomes? | Campaign, reply, account, contact, related properties, source date. | `CampaignSourceEvent`, `LeadSignal`, `RelatedOpportunityLink`. | Observe, classify, link, and recommend. | Rep confirms route and related-property treatment. |
| Site visit and discovery capture | LCW-04 to LCW-07 | Is onsite discovery required, and what project context must be captured? | Scope, site visit, room facts, photos, measurements, procurement context, rep memory. | `SiteVisitEvent`, `SiteVisitSummary`, `RoomContext`, `ProcurementContext`. | Prepare checklist, capture context, ask debrief questions, draft summary. | Rep confirms facts before downstream use. |
| Trade-in, flooring, and project branches | LCW-08 to LCW-09 | Which adjacent scopes affect quote, proposal, or handoff? | Existing equipment, extraction, trade-in value path, flooring vendor quote, flooring customer quote. | `ExistingEquipmentInventory`, `TradeInPacket`, `FlooringScope`. | Prepare packets and track dependencies. | Rep, vendor, or trade-in owner confirms scope and numbers. |
| Layout and product-fit reasoning | LCW-10 to LCW-12 | What layout and equipment package fit the property, room, and customer need? | Room context, layout direction, property tier, budget absence, multifamily fit, product catalog context. | `LayoutPlan`, `ProductSelectionRationale`, `ProposalPositioningNote`. | Recommend with rationale and expose assumptions. | Rep owns product and customer recommendation. |
| Quote and proposal readiness | LCW-13 to LCW-15 | Is the proposal package complete and safe to send? | Quote, F&I, trade-in, flooring, specs, layout, terms, recipient, message. | `QuoteReadinessChecklist`, `Quote`, `FreightInstallInputPacket`, `ProposalPackage`, `ProposalDeliveryEvent`. | Prepare checklist, assemble package, draft send message. | Rep approves customer-facing output. |
| Follow-up and decision state | LCW-16 | What is happening after proposal delivery? | Customer response, bid collection, follow-up touches, decision timing, stalled/no-response state. | `FollowUpState`, `FollowUpTask`, `BidCollectionStatus`. | Track state, remind, draft, and suggest next action. | Rep owns relationship-sensitive follow-up. |
| Approval and handoff readiness | LCW-17 to LCW-19 | Is approval real enough to mark closed-won, and what must carry forward? | Approval proof, quote version, site context, layout, trade-in, flooring, F&I, procurement notes. | `ApprovalProof`, `ClosedWonEvent`, `OrderReadinessInputState`. | Detect likely approval and prepare handoff context. | Rep/order owner confirms commitment and readiness boundary. |

## Key Context To Preserve

- Campaign provenance and source event.
- Account/property hierarchy, especially related-but-separate opportunities.
- Contact roles and procurement path.
- Site measurements, photos, sketches, flooring, existing equipment, access, and constraints.
- Product-fit rationale, including property tier, facility type, layout, and budget absence.
- Quote readiness dependencies such as F&I, trade-in, flooring, specs, terms, and proposal assets.
- Follow-up state, including bid collection versus no response.
- Approval proof and accepted quote version.
- Order-readiness input context for the post-close workflow.

## Risk And Autonomy

| Workflow Area | Risk Pattern | Recommended AI Role | Human Boundary |
| --- | --- | --- | --- |
| Source classification | Lost attribution or wrong route. | Observe, classify, link, and recommend. | Rep confirms opportunity and routing. |
| Site and project capture | Missing context can break layout, quote, delivery, or install. | Guide capture, draft summary, and ask debrief questions. | Rep reviews site facts. |
| Trade-in, flooring, and commercial branches | Wrong scope or numbers can create price and margin risk. | Prepare packets and track dependencies. | Rep/vendor/trade-in reviewer approves. |
| Layout and product selection | Wrong recommendation can lose trust or create bad customer fit. | Recommend with rationale only. | Rep owns judgment. |
| Quote/proposal | Customer-facing price, scope, and promise risk. | Prepare only. | Rep approves before sending. |
| Follow-up | Wrong pressure or tone can damage relationship. | Track, remind, and draft. | Rep acts. |
| Approval and handoff | False approval creates operational false progress. | Detect and prepare context. | Rep/order owner confirms. |

## Wiki And Agent Implications

This workflow supports these agent capability clusters:

- Source intelligence.
- Site-visit capture and debrief.
- Project-context readiness.
- Solution design support.
- Quote and proposal readiness.
- Follow-up and decision-state.
- Approval and handoff readiness.

It also demonstrates that a single `Lead` or `Quote` object is not enough. The workflow needs separate source, signal, site, room, layout, product rationale, quote, proposal, follow-up, approval, closed-won, and handoff objects/events.

## Open Validation Needs

- What product-fit factors explain expert rep judgment well enough to be reviewable?
- What follow-up state model should distinguish bid collection, no response, revision requested, won, lost, parked, and ignored?
- Which approval artifacts count as sufficient proof in different customer/procurement paths?
- What fields must be in the order-readiness input packet before post-close work can proceed?
