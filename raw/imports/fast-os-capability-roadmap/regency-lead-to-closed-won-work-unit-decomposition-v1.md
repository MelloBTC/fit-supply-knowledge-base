# Regency Lead-To-Closed-Won Work Unit Decomposition v1

Created: 2026-05-17

Status: Draft from existing Regency evidence

## Purpose

This artifact converts the Regency at Dell Ranch case from a case narrative into agent-ready FAST OS work units.

The goal is to identify what FAST OS would need to observe, decide, capture, prepare, review, and store as a real opportunity moves from outbound campaign response to approved quote and NetSuite closed-won.

This is not a post-close delivery workflow. The boundary is:

```text
outbound campaign response
-> site visit capture
-> layout-driven equipment selection
-> quote/proposal
-> bid waiting and follow-up
-> approval
-> NetSuite closed-won
-> order handoff boundary
```

The post-close workflow continues in:

[Regency Close-Won To Delivery Workflow Decomposition v1](regency-close-won-to-delivery-workflow-decomposition-v1.md)

## Source Boundary

This decomposition uses sanitized synthesis already in the repo. It does not copy raw emails, quote PDFs, pricing detail, customer signatures, photos, dimensions, or private project files into Git.

| Source | What It Contributes | Evidence Handling |
| --- | --- | --- |
| [Regency At Dell Ranch Outbound Campaign Response Case Study v1](../05-capability-roadmap/regency-at-dell-ranch-outbound-campaign-response-case-study-v1.md) | Timeline, source type, site visit, quote/proposal facts, product selection notes, approval, and closed-won boundary. | Evidence-backed where the case labels it as Josh walkthrough or raw artifact support. |
| [Regency Proposal Workflow Cross-Repo Synthesis v1](../05-capability-roadmap/regency-proposal-workflow-cross-repo-synthesis-v1.md) | Proposal workflow chain, room-context lessons, ECDESIGN/rendering boundaries, asset readiness, and proposal automation guardrails. | Sanitized synthesis from separate presentation-builder work. |
| [Regency Close-Won To Delivery Workflow Decomposition v1](regency-close-won-to-delivery-workflow-decomposition-v1.md) | The next lifecycle boundary after approval and closed-won conversion. | Used only to define the handoff boundary, not to pull delivery work backward into this artifact. |
| [Open Question Register v1](open-question-register-v1.md) | Central active questions for approval artifact detail, product-fit factors, follow-up states, and agent taxonomy. | Questions remain in the register unless answered here. |

## Business Outcome

Turn a campaign-generated customer response into a scoped, designed, quoted, approved, and handoff-ready won project.

FAST OS should help the dealer move from:

```text
customer expresses replacement need
```

to:

```text
approved project with enough structured context to begin order readiness review
```

without losing campaign attribution, site context, procurement context, product-selection reasoning, quote readiness, follow-up state, or approval proof.

## Lifecycle Scope

| Lifecycle Stage | Included? | Notes |
| --- | --- | --- |
| Lead Identification | Yes | Regency begins as an outbound campaign response. |
| Qualification | Yes | FAST OS needs to classify intent and quote-readiness distance. |
| Discovery | Yes | Customer need, timeline, ownership path, and procurement context are discovered. |
| Site Survey | Yes | Room measurements, photos, notes, flooring, existing equipment, and trade-in context are captured. |
| Layout & Design | Yes | Layout came before final equipment selection. |
| Equipment Selection | Yes | Product mix depended on room/layout, property tier, multifamily fit, and rep judgment. |
| Pricing & Quote Creation | Yes | QTE35768 was created; trade-in and F&I were requested and returned. |
| Proposal Assembly | Yes | Customer-facing proposal package was sent to the community manager. |
| Follow-Up & Objection Handling | Yes | Customer entered bid collection; Josh checked in. |
| Close & Procurement | Boundary | Approval received and quote converted to closed won. Order readiness begins next. |
| Delivery & Install | No | Covered by the post-close workflow artifact. |

## Workflow Spine

| Date | Event | State Change | Evidence Label |
| --- | --- | --- | --- |
| 2025-12-03 | Josh sent outbound follow-up / campaign-style email. | Campaign source event exists. | Evidence-backed |
| 2026-01-08 | Community manager replied that Regency and Madison were replacing all fitness equipment and asked for quote help. | Lead signal / replacement opportunity identified. | Evidence-backed |
| 2026-01-08 | Site visit scheduled for the next day. | Opportunity moved into discovery / site-visit prep. | Evidence-backed |
| 2026-01-09 | Regency site visit completed. | Site context, scope, measurements, photos, notes, flooring, and trade-in context began forming. | Evidence-backed |
| 2026-01-10 | QTE35768 created; trade-in and F&I requested. | Quote/proposal workflow started; quote readiness dependencies opened. | Evidence-backed |
| 2026-01-12 | Trade-in value received. | Trade-in context became usable in proposal path. | Evidence-backed |
| 2026-01-13 | F&I number received; QTE35768 sent. | Main proposal delivered to customer. | Evidence-backed |
| After 2026-01-13 | Manager confirmed receipt and said bids were being collected; Josh checked in. | Follow-up / bid-waiting state began. | Evidence-backed |
| 2026-02-19 | Approved quote received. | Sales opportunity became approved customer commitment. | Evidence-backed |
| After 2026-02-19 | Quote converted to closed won in NetSuite. | Sales workflow ended; order-readiness boundary began. | Evidence-backed |

## Work Unit Inventory

| ID | Work Unit | Recurring Decision | Required Context | Output | State Change | Risk If Wrong | AI Autonomy | Human Review | Evidence Label |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| LCW-01 | Preserve campaign source | Which outbound message produced this response? | Campaign, sent message, target account/contact, reply thread, send date | `CampaignSourceEvent` | Response linked to outbound effort | Medium: source quality and campaign learning are lost | Observe / record | Sales or marketing review as needed | Evidence-backed |
| LCW-02 | Detect replacement intent | Is the response a real opportunity? | Reply text, replacement language, timeline, scope, account/contact | `LeadSignal` | Campaign response becomes sales opportunity | Medium: warm opportunity can be missed or misrouted | Observe / recommend | Rep confirms | Evidence-backed |
| LCW-03 | Relate but separate properties | Are Regency and Madison one opportunity or related separate opportunities? | Shared management/ownership, separate sites, separate quotes, separate approvals | `RelatedOpportunityLink` | Related opportunities created without merging outcomes | Medium: quote, approval, and outcome tracking become inaccurate | Recommend with review | Rep confirms | Evidence-backed |
| LCW-04 | Schedule site visit | Is onsite discovery required before quoting? | Scope, quote-readiness distance, property location, contact availability, project complexity | `SiteVisitEvent` / visit plan | Opportunity moves into site-discovery state | Medium: quoting too early produces weak or wrong proposal | Prepare / recommend | Rep confirms | Evidence-backed |
| LCW-05 | Capture procurement context | What buying process controls the opportunity? | Three-bid requirement, community manager role, owner approval path, timing, competing vendors if known | `ProcurementContext` | Project strategy and follow-up state become structured | Medium: proposal and follow-up strategy can be wrong | Draft / prepare | Rep reviews | Evidence-backed |
| LCW-06 | Capture site and room context | What physical facts affect design, quote, delivery, and install? | Measurements, sketch, photos, doors/openings, constraints, existing equipment, flooring, access | `SiteVisitSummary`, `RoomContext`, `MeasurementSet`, `PhotoSet` | Site context becomes reusable project data | High: bad capture can break layout, quote, delivery, or install | Capture / prepare with review | Rep reviews; later PM/installer may validate | Evidence-backed |
| LCW-07 | Debrief rep after site visit | What did the rep learn that is not fully in notes/photos? | Rep memory, customer goals, decision path, scope nuance, unknowns, next actions | Reviewed `SiteVisitSummary` and missing-context questions | Unstructured memory becomes structured context | Medium: important context disappears after the visit | Draft / ask focused questions | Rep confirms | Evidence-backed / strong inference |
| LCW-08 | Inventory existing equipment and removal/trade-in scope | What is being removed, traded in, or replaced? | Photos, existing equipment, condition, trade-in value path, extraction responsibility | `ExistingEquipmentInventory`, `TradeInPacket`, `ExtractionScope` | Replacement and removal scope becomes quote/proposal input | Medium to high: price, scope, and handoff can be wrong | Prepare with review | Rep / trade-in owner | Evidence-backed |
| LCW-09 | Capture flooring scope | Is flooring part of the project and what must be quoted separately? | Room/flooring context, vendor quote, square footage/materials, transitions, install scope | `FlooringScope`, `VendorQuote`, `FlooringQuote` | Flooring branch enters proposal workflow | Medium: missing vendor scope creates rework or margin risk | Prepare with review | Rep / vendor quote owner | Evidence-backed |
| LCW-10 | Translate room context into layout direction | What layout best fits the room, goals, and existing constraints? | Room context, photos, desired zones, similar-layout direction, circulation, equipment categories | `LayoutPlan`, design direction | Layout becomes basis for product selection | High: layout error drives wrong equipment and bad proposal | Prepare / assist only | Rep/designer reviews | Evidence-backed |
| LCW-11 | Select product mix from layout and property fit | What equipment package fits the project? | Layout, property tier, multifamily use, customer request, manufacturer fit, budget absence, rep judgment | `ProductSelectionRationale`, quote line candidates | Recommended package becomes quote input | High: wrong package can lose deal or create bad customer fit | Recommend / prepare | Rep owns decision | Evidence-backed |
| LCW-12 | Handle no-budget proposal positioning | What package level should be proposed when no budget is given? | Property tier, market segment, customer goals, room capacity, expected usage, dealer judgment | `ProposalPositioningNote` | Quote/proposal receives package posture | Medium: over/under-scoping can reduce win probability | Recommend with rationale | Rep approves | Evidence-backed |
| LCW-13 | Request and incorporate quote-readiness dependencies | What dependencies must be resolved before sending? | Quote context, F&I need, trade-in value, flooring branch, install/extraction context | `QuoteReadinessChecklist`, dependency tasks | Quote moves toward send-ready | Medium to high: financial or scope assumptions may be wrong | Prepare / track | Rep and dependency owners | Evidence-backed |
| LCW-14 | Create main quote / proposal package | What customer-facing package should be sent? | Product mix, layout/design assets, trade-in, F&I, terms, specs, customer contact, proposal recipient | `Quote`, `ProposalPackage`, `ProposalDeliveryDraft` | Proposal ready for customer delivery | High: customer-facing price/scope/trust risk | Prepare only | Rep approves before send | Evidence-backed |
| LCW-15 | Send proposal and record delivery | Was the approved proposal sent to the right person with the right context? | Final quote, proposal package, recipient, email/message, send date | `ProposalDeliveryEvent` | Opportunity moves into awaiting-response state | Medium: wrong recipient/version or missing context affects deal | Draft / record | Rep sends or approves | Evidence-backed |
| LCW-16 | Track bid collection and follow-up state | What state is the customer in after proposal delivery? | Receipt confirmation, three-bid process, follow-up touches, decision timing, stalled/no-response state | `FollowUpState`, `FollowUpTask`, `BidCollectionStatus` | Opportunity moves from blank waiting to explicit state | Medium: follow-up leakage or wrong urgency | Recommend / draft reminders | Rep owns customer follow-up | Evidence-backed |
| LCW-17 | Capture approval and likely win reason | Has the customer approved, and what do we know about why? | Approved quote, approval date, signer/artifact if available, rep notes, known/unknown win reason | `ApprovalSignal`, `WinReasonNote` | Opportunity moves toward closed-won review | High: false approval can trigger bad operations work | Observe / prepare | Rep confirms | Evidence-backed |
| LCW-18 | Convert to closed won | Is the approval sufficient to move from sales proposal to won project? | Approved quote/PO/email, quote version, customer commitment, order handoff needs | `ClosedWonEvent` | Sales workflow ends; order readiness begins | High: operations may act before commitment/context is valid | Prepare only | Rep/order owner confirms | Evidence-backed |
| LCW-19 | Prepare order-readiness handoff boundary | What context must carry into post-close workflow? | Approved quote, site context, layout, trade-in/extraction, flooring, F&I, procurement notes, customer/rep context | `OrderReadinessInputState` | Post-close workflow can start without rediscovery | High: missing context causes order, PO, delivery, or install errors | Prepare with review | Rep and PM/order owner | Strong inference |

## Decision Inventory

| Decision | Where It Happens | Why It Matters | Current Evidence | Human Owner |
| --- | --- | --- | --- | --- |
| Is the email response a real opportunity? | Campaign response review | Determines whether FAST OS routes to site visit and quote workflow. | Customer asked for help with replacement quote. | Rep |
| Should related properties be tracked separately? | Lead/opportunity creation | Regency and Madison share management context but have separate quotes and approvals. | Josh confirmed separate quoting and approvals. | Rep |
| Is a site visit required before quote? | Discovery / qualification | Regency was quote-plausible but not quote-ready from email alone. | Site visit, measurements, photos, flooring, trade-in, and design were needed. | Rep |
| What procurement context matters? | Discovery / site visit | Three vendor bids affects follow-up, urgency, and proposal strategy. | Manager was collecting three bids. | Rep |
| What room facts are proposal-ready? | Site visit / design prep | Layout and equipment fit depend on accurate enough room context. | Measurements and handwritten notes were captured manually. | Rep/designer |
| What old equipment is removed or traded in? | Site visit / quote readiness | Trade-in and extraction affect pricing and handoff. | Trade-in value was requested and received. | Rep / trade-in reviewer |
| What flooring branch exists? | Site visit / quote readiness | Flooring had vendor and customer quote paths separate from main equipment quote. | Redi Carpet quote and QTE35970 exist. | Rep / vendor quote owner |
| What product mix fits? | Layout and product selection | Customer wanted recommendations; layout clarified equipment needs. | Product selection happened after layout. | Rep |
| How should FAST OS unpack "felt like the right fit"? | Equipment selection | Expert judgment must become reviewable reasons without pretending to be fully objective. | Multifamily fit, property tier, and vertical-market line were captured. | Rep |
| What should be sent to the customer? | Proposal assembly | Proposal must match quote, visuals, specs, trade-in, F&I, and scope. | QTE35768 was sent as the only Regency quote. | Rep |
| What follow-up state exists after send? | Proposal follow-up | Bid collection is not the same as no response. | Manager confirmed receipt and was collecting bids. | Rep |
| Is the customer approval sufficient for closed-won? | Close boundary | Approval should not trigger operations unless commitment is real. | Approved quote received 2026-02-19; exact artifact type remains open. | Rep / order owner |
| What must carry into order readiness? | Handoff boundary | Closed-won is not automatically order-ready. | Post-close workflow separately validates order readiness. | Rep and PM/order owner |

## Context Inventory

| Context Area | Why FAST OS Needs It | Evidence Label |
| --- | --- | --- |
| Campaign provenance | Needed to measure which outbound messages become site visits, quotes, wins, and delivered projects. | Evidence-backed |
| Account/property hierarchy | Regency and Madison must be linked but not merged. | Evidence-backed |
| Contact and role context | Community manager was the onsite contact; ownership was likely final decision maker. | Evidence-backed |
| Replacement intent | The response stated replacement of all fitness equipment soon. | Evidence-backed |
| Procurement rule | Three vendor bids required changes sales strategy and follow-up state. | Evidence-backed |
| Site measurements and photos | Needed for layout, equipment selection, proposal, delivery, and install readiness. | Evidence-backed |
| Customer goal and design direction | Customer was open to redesign, but final direction kept a similar layout. | Evidence-backed |
| Existing equipment and extraction | Old equipment removal and trade-in affected quote and handoff context. | Evidence-backed |
| Flooring scope | Flooring created a parallel vendor/customer quote path. | Evidence-backed |
| Budget absence | No budget was provided, so proposal positioning relied on property tier and rep judgment. | Evidence-backed |
| Product-fit rationale | Light commercial / vertical-market fit and multifamily suitability explain the selected line. | Evidence-backed |
| Proposal delivery and follow-up | Needed to track bid collection, stalled state, and quote outcome. | Evidence-backed |
| Approval proof | Needed before closed-won and order readiness. Exact Regency artifact still needs validation. | Evidence-backed / needs Josh validation |
| Win reason | Customer likely liked equipment selection and layout, but Josh was not certain. | Evidence-backed uncertainty |

## Output And State Inventory

| Output Or State | Produced By | Used Later By | Candidate Object / Event |
| --- | --- | --- | --- |
| Campaign source event | Outbound campaign / email capture | Lead attribution and campaign learning | `CampaignSourceEvent` |
| Lead signal | Response classification | Qualification and routing | `LeadSignal` |
| Related opportunity link | Account/property modeling | Quote and outcome separation | `RelatedOpportunityLink` |
| Site visit plan/event | Scheduling and prep | Site capture and debrief | `SiteVisitEvent`, `SiteVisitPlan` |
| Procurement context | Discovery capture | Follow-up, proposal strategy, close tracking | `ProcurementContext` |
| Site visit summary | Mobile capture / debrief | Layout, quote, proposal, handoff | `SiteVisitSummary` |
| Room context | Measurement/photo capture | Layout, equipment fit, proposal visuals | `RoomContext`, `MeasurementSet` |
| Existing equipment inventory | Site capture / photos | Trade-in, extraction, proposal, handoff | `ExistingEquipmentInventory` |
| Trade-in packet | Trade-in workflow | Quote and approval package | `TradeInPacket`, `TradeInCredit` |
| Flooring scope | Site visit / vendor quote | Flooring quote, proposal, handoff | `FlooringScope`, `VendorQuote`, `FlooringQuote` |
| Layout plan | Design workflow | Product selection and proposal visuals | `LayoutPlan`, `DesignPackage` |
| Product selection rationale | Rep/design judgment | Quote, proposal explanation, future learning | `ProductSelectionRationale` |
| Quote readiness checklist | Quote preparation | Proposal send decision | `QuoteReadinessChecklist` |
| Main proposal package | Quote/proposal workflow | Customer review and approval | `Quote`, `ProposalPackage` |
| Proposal delivery event | Rep send action | Follow-up and outcome tracking | `ProposalDeliveryEvent` |
| Follow-up state | Rep/customer interaction | Stalled/won/lost learning | `FollowUpState`, `FollowUpTask` |
| Approval signal | Customer approval | Closed-won review | `ApprovalSignal`, `ApprovalProof` |
| Closed-won event | Rep/order owner | Post-close workflow | `ClosedWonEvent` |
| Order readiness input state | Handoff boundary | Order readiness validation | `OrderReadinessInputState` |

## Risk And Autonomy Matrix

| Work Unit Range | Risk Pattern | Recommended AI Role | Human Boundary |
| --- | --- | --- | --- |
| LCW-01 to LCW-03 | Misclassification or lost attribution | Observe, classify, link, and recommend | Rep confirms opportunity and related-property treatment. |
| LCW-04 to LCW-07 | Missing site/project context | Prepare visit checklist, capture notes/photos, ask debrief questions, draft summary | Rep confirms site facts before downstream use. |
| LCW-08 to LCW-09 | Commercial scope errors around trade-in, extraction, and flooring | Prepare packets and track dependencies | Rep/vendor/trade-in reviewer confirms numbers and scope. |
| LCW-10 to LCW-12 | Wrong layout, product mix, or package level | Recommend with rationale and expose assumptions | Rep owns layout/product judgment and customer-facing recommendation. |
| LCW-13 to LCW-15 | Customer-facing price/scope/proposal risk | Prepare checklist, assemble package, draft send message | Rep approves before customer delivery. |
| LCW-16 | Follow-up leakage or wrong customer pressure | Track state, draft reminders, suggest next touch | Rep owns relationship-sensitive follow-up. |
| LCW-17 to LCW-19 | False approval or weak handoff | Detect approval, prepare closed-won/handoff context | Rep/order owner confirms approval and handoff readiness. |

## Capability Implications

| Capability Candidate | Supported Work Units | User Value | Dependencies | Confidence |
| --- | --- | --- | --- | --- |
| Outbound response intelligence | LCW-01, LCW-02, LCW-03 | Converts campaign replies into routed, attributed, measurable opportunities. | Email/campaign capture, account/contact matching, source provenance. | Evidence-backed / strong inference |
| Site visit capture and debrief | LCW-04, LCW-05, LCW-06, LCW-07 | Reduces manual notes, memory loss, and post-visit rework. | Mobile capture, photos, measurement input, voice/chat debrief, review events. | Evidence-backed |
| Project-context readiness | LCW-06 through LCW-09 | Makes site, trade-in, flooring, and procurement context available to quote/proposal work. | Structured site context, asset inventory, source links, unknown handling. | Strong inference |
| Layout-driven equipment selection support | LCW-10, LCW-11, LCW-12 | Helps reps justify product recommendations from room, property, and usage context. | Room context, product catalog, segment fit, rep review, design assets. | Evidence-backed / strong inference |
| Quote/proposal readiness | LCW-13, LCW-14, LCW-15 | Ensures proposal is send-ready before customer-facing output. | Quote, F&I, trade-in, flooring, specs, layout, review. | Evidence-backed |
| Follow-up and bid-state tracking | LCW-16 | Prevents bid collection and decision-pending states from becoming invisible. | Proposal delivery event, customer responses, reminders, outcome tracking. | Evidence-backed |
| Approval and handoff readiness | LCW-17, LCW-18, LCW-19 | Prevents closed-won from becoming a weak operations handoff. | Approval proof, accepted quote version, order-readiness packet, review. | Evidence-backed / strong inference |

## Schema Implications

| Object / Event / Artifact | Why It Is Needed | Source / Provenance Need | Review / Audit Need |
| --- | --- | --- | --- |
| `CampaignSourceEvent` | Preserves outbound campaign origin. | Link to sent message, reply thread, account/contact, campaign. | Light review unless attribution is uncertain. |
| `LeadSignal` | Represents the possible sales opportunity created by the response. | Source email and classification reason. | Rep confirmation. |
| `RelatedOpportunityLink` | Keeps related properties connected without merging quotes/outcomes. | Management/ownership relationship and separate quote IDs. | Rep/account review. |
| `ProcurementContext` | Stores bid requirements, approval path, and decision timing. | Customer conversation or email evidence. | Rep review. |
| `SiteVisitEvent` | Records scheduled and completed site visits. | Calendar/email/site notes. | Rep review. |
| `SiteVisitSummary` | Converts notes/photos/debrief into structured project context. | Field notes, photos, rep debrief, confidence labels. | Rep approval before quote use. |
| `RoomContext` | Carries geometry and constraints into layout/design. | Measurements, sketches, photos, confidence. | Review before design/proposal reliance. |
| `ExistingEquipmentInventory` | Separates current equipment from proposed equipment. | Photos, notes, quote/trade-in artifacts. | Rep/trade-in review. |
| `TradeInPacket` | Supports value, removal, extraction, and commercial treatment. | Trade-in photos/value/source. | Human approval. |
| `FlooringScope` | Keeps flooring scope distinct from main equipment quote. | Site notes, vendor quote, flooring quote. | Rep/vendor quote review. |
| `LayoutPlan` | Connects room context to product selection and proposal visuals. | Design artifact/version/source tool. | Rep/designer review. |
| `ProductSelectionRationale` | Makes expert judgment reviewable and learnable. | Rep explanation, product catalog, segment fit, layout context. | Rep owns final rationale. |
| `QuoteReadinessChecklist` | Tracks dependencies before customer proposal delivery. | F&I, trade-in, flooring, quote, terms, specs. | Rep approval. |
| `ProposalPackage` | Represents customer-facing proposal state. | Approved quote version, assets, specs, terms. | Rep approval and audit. |
| `ProposalDeliveryEvent` | Records what was sent, to whom, and when. | Email/message, proposal version, recipient. | Audit. |
| `FollowUpState` | Prevents blank waiting periods. | Customer response, bid state, reminders, rep notes. | Rep review. |
| `ApprovalProof` | Establishes approval threshold. | Signed quote, PO, or approval email. | Human confirmation required. |
| `ClosedWonEvent` | Marks transition from sales to post-close workflow. | Approval proof and accepted quote. | Audit event. |
| `OrderReadinessInputState` | Carries sales context into order readiness. | Quote, site, trade-in, flooring, F&I, procurement context. | Rep/PM review. |

## Emerging Agent Candidate Clusters

These are not final agent names. They are candidate clusters that emerge from the Regency work units.

| Candidate Cluster | Work Units Included | Shared Context / Tools | Autonomy Boundary | Validation Needed |
| --- | --- | --- | --- | --- |
| Source intelligence cluster | LCW-01, LCW-02, LCW-03 | Email/campaign data, account/contact matching, source type, related opportunity logic | Observe, classify, and recommend; rep confirms route | Compare outbound response against more campaign responses. |
| Site-visit capture cluster | LCW-04, LCW-05, LCW-06, LCW-07 | Calendar/email, mobile capture, photos, measurements, rep debrief, procurement context | Prepare/capture/draft; rep confirms facts | Validate site survey field list and mobile workflow. |
| Project-context readiness cluster | LCW-08, LCW-09, LCW-10 | Existing equipment, trade-in, flooring, room context, layout assets | Prepare packets and readiness checks; humans approve commercial scope | Validate trade-in/flooring handoffs across cases. |
| Solution design support cluster | LCW-10, LCW-11, LCW-12 | Room context, property tier, product catalog, segment fit, rep judgment | Recommend with rationale; rep owns selection | Unpack product-fit factors across more quote cases. |
| Quote/proposal readiness cluster | LCW-13, LCW-14, LCW-15 | Quote, F&I, trade-in, flooring, proposal assets, recipient, send event | Prepare only; rep approves customer-facing output | Compare Regency with Park and larger proposal cases. |
| Follow-up and decision-state cluster | LCW-16, LCW-17 | Proposal delivery, customer response, bid collection, approval signal, win/loss reason | Track, remind, draft; rep owns relationship | Define follow-up state model across Park and Regency. |
| Approval/handoff readiness cluster | LCW-17, LCW-18, LCW-19 | Approval proof, accepted quote, order-readiness context, post-close packet | Prepare and validate; human confirms commitment and handoff | Validate exact approval artifacts and order handoff completeness. |

## Open Questions And Validation Needed

Use [Open Question Register v1](open-question-register-v1.md) as the active control document. The questions most directly touched by this decomposition are:

| Register ID | Why It Matters Here |
| --- | --- |
| OQ-008 | Product-fit factors need more detail so FAST OS can unpack "felt like the right fit" into reviewable reasons. |
| OQ-012 | Bid collection, no response, decision pending, revision requested, won, lost, and parked states need a consistent follow-up model. |
| OQ-013 | The exact Regency approval artifact remains useful for validating `ApprovalProof`, though not blocking for the broad workflow. |
| OQ-014 | Order handoff packet completeness is the next boundary after this artifact. |
| OQ-022 | This decomposition should feed the cross-stage agent candidate inventory. |

## Synthesis Notes

| Type | Note |
| --- | --- |
| Evidence-backed | Regency validates outbound campaign response as a first-class lead source. |
| Evidence-backed | Regency and Madison should be related but separately quoted, approved, and tracked. |
| Evidence-backed | The email response was not enough to quote; site visit and room/project capture were required. |
| Evidence-backed | Layout came before final equipment selection. |
| Evidence-backed | Budget absence is a recurring proposal-positioning condition, not just missing data. |
| Evidence-backed | Three vendor bids should be structured procurement context. |
| Evidence-backed | QTE35768 was created on 2026-01-10, sent on 2026-01-13, approved on 2026-02-19, and converted to closed won. |
| Evidence-backed uncertainty | Josh is not certain why Regency approved, but he believes the customer liked the equipment selection and layout. |
| Strong inference | FAST OS should produce an order-readiness input packet at closed-won so post-close work does not rediscover site, trade-in, flooring, F&I, and procurement context. |
| Product implication | Regency connects lead-source intelligence, site-visit capture, solution design, proposal readiness, follow-up, approval, and handoff readiness into one continuous agent-design test case. |
| Schema implication | The workflow should not collapse into one `Lead` or `Quote`; it requires separate source, signal, site, room, selection, quote, proposal, follow-up, approval, closed-won, and handoff objects/events. |

## Recommended Next Use

Use this artifact to draft the first cross-stage agent candidate inventory:

```text
source intelligence cluster
-> site-visit capture cluster
-> project-context readiness cluster
-> solution design support cluster
-> quote/proposal readiness cluster
-> follow-up and decision-state cluster
-> approval/handoff readiness cluster
-> post-close order coordination cluster
```

The next artifact should not finalize agent names. It should compare the clusters emerging from Regency against Park, Bailey, Lenox, TSU, and the post-close Regency workflow to see which boundaries repeat.
