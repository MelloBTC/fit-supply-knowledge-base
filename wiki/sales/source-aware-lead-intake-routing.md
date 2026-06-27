---
title: Source-Aware Lead Intake And Routing
type: Workflow
domain: sales
knowledge_scope: target-state
status: Draft
last_reviewed:
reviewed_by:
sources:
  - raw/imports/fast-os-capability-roadmap-source-inventory.md#fscr-016
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/05-capability-roadmap/source-aware-lead-intake-routing-capability-card-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/05-capability-roadmap/source-aware-lead-intake-research-data-model-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/05-capability-roadmap/lead-source-taxonomy-and-routing-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/05-capability-roadmap/lead-research-data-enrichment-workflow-decomposition-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/05-capability-roadmap/park-at-rialto-service-referral-case-study-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/05-capability-roadmap/texas-southern-university-owner-forwarded-lead-case-study-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/05-capability-roadmap/lenox-park-inbound-equipment-request-case-study-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/05-capability-roadmap/bailey-at-berkman-constructconnect-lead-case-study-v1.md
related:
  - [[lead-to-closed-won-workflow|Lead To Closed Won Workflow]]
  - [[hunter-sales-existing-multifamily-pattern|Hunter Sales Existing Multifamily Pattern]]
  - [[../knowledge-base/distributor-workflow-map|Distributor Workflow Map]]
  - [[../knowledge-base/agent-capability-map|Agent Capability Map]]
  - [[../knowledge-base/agent-answerability-targets|Agent Answerability Targets]]
  - [[../knowledge-base/domain-model-review|Domain Model Review]]
agent_answerability:
  - How should a future agent classify a lead by source type before choosing the first workflow?
  - Which source-specific first output should be prepared for service-created, owner-forwarded, inbound bid, or formal-feed lead signals?
  - What information must be preserved so lead sources can be reviewed, assigned, followed up, and measured honestly?
  - When should a lead be routed to research/enrichment instead of quote readiness or pursuit planning?
tags:
  - sales-workflow
  - lead-intake
  - source-intelligence
  - routing
  - roadmap-derived
provenance_notes: Synthesized from the roadmap source-aware lead intake family and four mapped source cases. This page generalizes the workflow without importing raw customer, pricing, quote, or NetSuite artifacts.
---

# Source-Aware Lead Intake And Routing

This page captures the target-state workflow for turning lead signals into reviewed, assigned, followed-up sales work. It sits before [[lead-to-closed-won-workflow|Lead To Closed Won Workflow]] and explains how the system should decide which first workflow a lead deserves.

The central rule is simple:

```text
the lead record is not enough
```

FAST OS needs to preserve the source event, classify the source type, assess quote-readiness distance, recommend the first route, prepare the right first output, assign an owner or explicit no-action state, and track what happened.

## Source Boundary

The supporting roadmap artifacts include real case-derived learning, but this page does not import raw customer emails, quote PDFs, pricing details, NetSuite exports, source-feed pages, or private attachments into the wiki.

The four evidence patterns are:

| Pattern | Evidence Role | Wiki Treatment |
| --- | --- | --- |
| Service-created replacement signal | Shows service findings can create credible replacement demand, but quote and follow-up context can leak across systems. | Use as a source-type pattern, not as a service or quote artifact import. |
| Owner-forwarded project intelligence | Shows a human-forwarded project signal may need enrichment, pursuit planning, task ownership, and outcome tracking. | Preserve evidence labels because generated plans can mix facts and assumptions. |
| Inbound bid or equipment request | Shows direct buyer requests should move quickly toward account matching, product-request extraction, quote-readiness questions, and follow-up. | Do not over-process as a broad research workflow. |
| Formal project intelligence feed | Shows formal feed items can be human-curated before the rep acts and may need source preservation, fit review, research, and park/pursue decisions. | Keep raw feed and NetSuite details out of the wiki unless intentionally sanitized later. |

## Business Outcome

Turn incoming lead signals into useful sales motion without creating a noisy lead list.

```text
source event arrives
-> source type is classified
-> account, property, contact, project, or installed asset is matched
-> quote-readiness distance is assessed
-> first route and first output are recommended
-> human review confirms action-sensitive choices
-> owner and next action are recorded
-> outreach, quote, park, reject, ignored, no-response, won, or lost outcome is tracked
-> source quality learning improves future routing
```

The workflow should optimize for reviewed action and honest outcomes, not impressive lead artifacts.

## Source Types And Default Routes

| Lead Source Type | Default First Route | First Output | Human Review Boundary |
| --- | --- | --- | --- |
| Service-created replacement signal | Replacement opportunity and quote-readiness path. | Replacement opportunity brief with service evidence, failed assets, account context, quote blockers, and follow-up plan. | Rep reviews product direction, extraction assumptions, quote package, and customer communication. |
| Owner-forwarded or human-forwarded project intelligence | Enrichment and pursuit-planning path. | Source-aware pursuit plan with project facts, opportunity angles, procurement questions, immediate tasks, and review needs. | Rep or manager reviews source facts, contacts, procurement assumptions, outreach path, and assignment. |
| Inbound bid or equipment request | Quote-readiness acceleration path. | Inbound readiness summary with account/contact match, requested product summary, missing quote inputs, and response or quote-prep draft. | Rep reviews product interpretation and any customer-facing quote, price, or reply. |
| Formal project intelligence feed | Ingest, dedupe, research, fit review, and assignment path. | Formal-feed research brief with source facts, human-curation note, internal context, amenity relevance, buyer path, timing, and recommended action. | Human reviews fit, owner, contact path, and pursue/park/reject/monitor decision. |
| Manufacturer, vendor, or partner referral | Referral-context qualification path. | Referral brief with source, relationship context, requested action, urgency, and next step. | Rep or manager reviews relationship handling and customer outreach. |
| Existing account or lifecycle trigger | Proactive account opportunity path. | Lifecycle opportunity signal with account history, installed-base or service evidence, and suggested outreach. | Rep reviews timing and claim strength. |
| Website, form, phone, or low-confidence inquiry | Intent triage path. | Inbound request record or review item. | Human confirms ambiguous routing and response. |

## Quote-Readiness Distance

Source type alone is not enough. The system should also name how close the lead is to a quote.

| Distance | Meaning | Default Move |
| --- | --- | --- |
| `quote_ready_or_nearly_ready` | Buyer asks for a bid or quote and product need is visible. | Extract request, identify missing quote fields, and prepare response or quote package for review. |
| `quote_plausible_context_incomplete` | Need is credible, but product, site, freight/install, buyer, or pricing context is incomplete. | Build opportunity brief and quote-readiness checklist. |
| `pursuit_worthy_not_quote_ready` | Project or account may be valuable, but buyer path, fit, stakeholders, timing, or source confidence need work. | Enrich, qualify, plan, assign, monitor, or park. |
| `low_confidence_signal` | Source, fit, timing, or account match is unclear. | Create review item, dedupe, enrich minimally, and avoid rep overload. |

This distinction prevents two common mistakes: treating a direct bid request like a research project, and treating a thin project-intelligence feed like a quote-ready opportunity.

## Work Unit Spine

| ID | Work Unit | Decision | Required Context | Output / State | AI Posture | Human Boundary |
| --- | --- | --- | --- | --- | --- | --- |
| LSR-01 | Preserve source event | What entered the system, from where, and when? | Email, task, source feed, attachment, sender/channel, timestamp, source path. | `SourceEvent`. | Observe and record when access is authorized. | Review sensitive source handling. |
| LSR-02 | Classify lead source type | What kind of signal is this? | Source event, sender role, channel, intent language, service/project/inbound clues. | `LeadSourceType`. | Recommend with correction. | Human can correct route class. |
| LSR-03 | Match account, contact, project, property, or asset | What business context does this signal belong to? | Account records, sender domain, property name, CRM/ERP history, service history, source text. | Match recommendation and confidence. | Recommend with source evidence. | Human reviews low-confidence or duplicate matches. |
| LSR-04 | Assess quote-readiness distance | How close is this signal to quote work? | Buyer intent, product need, service evidence, project timing, missing context, prior history. | `QuoteReadinessDistance`. | Recommend with explanation. | Human can override. |
| LSR-05 | Select first routing path | Which workflow should start first? | Source type, quote-readiness distance, owner, risk, missing facts, current stage. | `LeadRouteDecision`. | Recommend. | Human confirms action-changing choices early. |
| LSR-06 | Build source-specific first output | What does the rep need first? | Service facts, project facts, product request, account history, relationship context. | Replacement brief, pursuit plan, inbound summary, referral brief, or research brief. | Prepare. | Rep reviews before outreach or quote work. |
| LSR-07 | Identify missing context | What blocks the next useful action? | Required route fields, quote blockers, stakeholder gaps, product ambiguity, source confidence. | Missing-context list or quote blockers. | Prepare. | Human validates commercial and customer-facing implications. |
| LSR-08 | Assign owner and next action | Who should do what next, by when? | Brief, owner, urgency, channel, due date, policy. | `AssignmentEvent` and `FollowUpTask`. | Prepare or execute with accepted policy. | Human approves in early versions or ambiguous cases. |
| LSR-09 | Track execution and outcome | Did the lead become action, quote, revenue, or learning? | Tasks, replies, outreach, opportunity, quote, win/loss, parked/no-action reason. | `ConversionStatus` and `SourceOutcome`. | Observe and recommend. | Human confirms ambiguous outcomes. |
| LSR-10 | Learn source quality | Which sources and routes create useful sales motion? | Outcomes, corrections, ignored leads, conversion, effort, source cost if available. | `SourceQualitySignal`. | Observe and recommend. | Human validates source-investment decisions. |

## Research And Enrichment Subloop

Formal project intelligence and some owner-forwarded leads should not jump straight to outreach or quote preparation. They need a bounded research subloop:

```text
route decision says research is needed
-> define source-type-aware research questions
-> retrieve internal account/project/contact context
-> preserve original source context separately from human curation
-> enrich project, account, amenity, buyer-path, and timing facts
-> label facts, inferences, confidence, and gaps
-> prepare research brief
-> rep reviews, corrects, pursues, parks, rejects, monitors, or asks for more research
-> research outcome updates source quality and route learning
```

This subloop is especially important when a formal lead feed has enough context to be plausible but not enough fitness, amenity, buyer, or timing evidence to justify immediate pursuit.

## State And Outcome Model

Every lead should have a visible state. Silent limbo is one of the problems the system is meant to solve.

```text
source_captured
-> lead_signal_created
-> classified
-> matched
-> route_recommended
-> review_needed
-> research_needed / ready_for_review
-> reviewed
-> assigned
-> action_in_progress
-> outcome_recorded
```

Valid terminal or holding states should include:

- `converted_to_opportunity`
- `quote_sent`
- `won`
- `lost`
- `parked`
- `monitoring`
- `rejected_not_fit`
- `ignored`
- `no_response`
- `no_action`

`ignored` and `no_action` should be explicit states. Missing data cannot teach the system whether a source creates value or noise.

## Schema Implications

The page does not define implementation schema, but it identifies object families future schema work will need:

| Layer | Candidate Objects Or Events |
| --- | --- |
| Source and provenance | `LeadSource`, `SourceEvent`, `SourceAttachmentRef`, `SourceChannel`, `SourceConfidence`, `SourceContextPacket`. |
| Lead signal and routing | `LeadSignal`, `LeadSourceType`, `QuoteReadinessDistance`, `LeadRouteDecision`, `RoutingReason`. |
| Human curation | `LeadCurationEvent`, `CurationNote`, `CuratedField`, `OmittedField`. |
| Account and project context | `Account`, `Property`, `Site`, `Project`, `Contact`, `RelationshipLink`, `DuplicateCandidate`. |
| Research and enrichment | `ResearchQuestionSet`, `ResearchRun`, `InternalContextSummary`, `EnrichedProjectProfile`, `AmenityRelevanceSignal`, `BuyerPathHypothesis`, `TimingReadinessSignal`, `LeadResearchBrief`, `ResearchReviewEvent`, `ResearchOutcome`. |
| Assignment and execution | `AssignmentEvent`, `FollowUpTask`, `Interaction`, `OutreachDraft`, `Opportunity`, `QuoteIntent`. |
| Outcome and learning | `ConversionStatus`, `SourceOutcome`, `SourceQualitySignal`, `CorrectionSignal`. |
| Review and trust | `EvidenceLabel`, `Confidence`, `Suggestion`, `ReviewEvent`, `HumanApproval`, `AuditEvent`. |
| Playbook governance | `WorkflowPlaybook`, `PlaybookVersion`, `TriggerRule`, `OutputTemplate`, `GovernanceStatus`. |

## Human Review Rules

| Action | Early FAST OS Posture |
| --- | --- |
| Preserve authorized source event | Execute automatically. |
| Classify source type | Recommend automatically with correction. |
| Match account/contact/project | Recommend with source evidence. |
| Assess quote-readiness distance | Recommend with explanation. |
| Select route | Recommend. |
| Generate brief, research packet, or plan | Prepare for review. |
| Draft outreach | Draft only. |
| Prepare quote-related output | Prepare only. |
| Send outreach or customer-facing quote | Human approves and sends. |
| Mark parked, rejected, no-action, lost, or source-quality conclusion | Recommend; human confirms unless an approved policy exists. |
| Promote reusable playbook | Draft only; product/admin review required. |

## Wiki And Agent Implications

This workflow strengthens the `source intelligence`, `research and enrichment`, `inbound quote-readiness`, `follow-up and decision-state`, and `playbook governance` capability clusters in [[../knowledge-base/agent-capability-map|Agent Capability Map]].

It also clarifies the relationship between lead intake and later workflow pages:

- This page decides what kind of lead signal has arrived and what first route it deserves.
- [[lead-to-closed-won-workflow|Lead To Closed Won Workflow]] begins after a lead has enough sales context to move through discovery, quote/proposal, follow-up, approval, and closed-won.
- [[hunter-sales-existing-multifamily-pattern|Hunter Sales Existing Multifamily Pattern]] remains a design-hypothesis policy lane for proactive prospecting and reactivation. It should not be treated as the approved policy default for all source-aware lead routing.

Keep `lead-intelligence` and `prospecting` as sales sub-lanes for now. This page creates more navigation pressure, but not enough validated page density to justify a new top-level domain.

## Open Validation Needs

- Confirm the first evidenced source types against 10 to 15 real or sanitized lead examples.
- Validate which fields make a lead `actionable` rather than merely `captured`.
- Decide who owns ambiguous lead triage: rep, owner, manager, admin, or shared review queue.
- Validate the minimum research brief that saves rep time without becoming noisy.
- Confirm whether high-intent inbound requests should always create follow-up tasks.
- Test raw formal feed, referral, manufacturer, website, phone, or municipal RFP artifacts against the taxonomy.
- Validate which outcome states reps and owners will actually maintain.
- Preserve the boundary that product/pricing/catalog answerability remains upstream-owned until mature enough to consume here.
