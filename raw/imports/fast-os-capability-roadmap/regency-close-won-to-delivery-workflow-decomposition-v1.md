# Regency Close-Won To Delivery Workflow Decomposition v1

Created: 2026-05-17

Status: Draft from Josh walkthrough

## Purpose

This note captures the workflow that begins when a customer approves a quote and ends when the completed installation moves into relationship management.

The goal is not to recreate Fit Supply's NetSuite workflow. NetSuite and the current Fit Supply process are evidence of today's coordination pattern. FAST OS should design a cleaner workflow around the real business outcome:

```text
approved customer commitment
-> clean order handoff
-> payment and vendor coordination
-> site readiness
-> delivery and installation readiness
-> install completion evidence
-> rep/customer relationship continuity
```

The strongest product read is:

```text
project management after close-won is coordination-heavy, mechanical, and relationship-sensitive.
FAST OS should automate the mechanical tracking and preparation work
while preserving human-in-the-loop review for payment, customer commitments, vendor actions, delivery readiness, and relationship moments.
```

## Source Boundary

| Source | Type | What It Supports | Confidence |
| --- | --- | --- | --- |
| Josh walkthrough on 2026-05-17 | Direct workflow explanation | Approval requirements, order handoff, payment terms, vendor PO flow, customer status updates, site survey, delivery prep, installation evidence, sales-rep visibility, and relationship-management transition. | Evidence-backed |
| Regency case study | Active case context | QTE35768 approval on 2026-02-19 and conversion to closed won after customer approval. | Evidence-backed |
| Current Fit Supply / NetSuite process | Current-state evidence | Shows how order handoff, sales order creation, new order notes, deposit invoice, and team handoff happen today. | Evidence-backed as current workflow only |
| Back-office best-practice research | Future supplement | Needed because Josh has limited visibility into detailed back-office order, purchasing, accounting, and logistics processes. | Needs research |

## Design Boundary

FAST OS should not assume the current system's screen sequence is the ideal workflow.

Current-state evidence:

```text
signed quote / PO received
-> quote converted to closed won
-> sales order created
-> orders team receives it
-> project manager adds reminders / notes
-> deposit invoice and vendor purchase orders are created
-> customer, vendor, installation company, and sales rep are coordinated
```

FAST OS target workflow:

```text
approval proof captured
-> order readiness validated
-> handoff packet generated
-> payment terms and invoice milestones managed
-> vendor procurement coordinated
-> customer status updates generated and reviewed
-> site survey and install readiness packet completed
-> delivery scheduled after equipment receipt
-> completion evidence captured
-> relationship-management flow starts
```

## Lifecycle Scope

| Lifecycle Stage | Included? | Notes |
| --- | --- | --- |
| Close, approval, and quote-to-order handoff | Yes | Starts when signed quote or customer PO is received. |
| Procurement, vendor, freight, and order coordination | Yes | Includes sales order, deposit invoice, vendor purchase orders, payment status, lead times, and vendor coordination. |
| Delivery, installation, and project completion | Yes | Includes site survey, delivery prep packet, equipment shipment to installation company, scheduling, install photos, and customer sign-off. |
| Warranty, service, PM, and installed-base lifecycle | Boundary only | Starts after completed install and installed equipment context are captured. |
| Account expansion, renewal, replacement, and future demand | Boundary only | Relationship management flow starts after delivery completion. |

## Workflow Loop

Observed current-state loop:

```text
signed quote or PO received
-> quote converted to closed won
-> sales order is created and sent to orders team
-> project manager reviews order and notes
-> deposit invoice is created based on terms
-> purchase orders are sent to vendors
-> customer receives payment and lead-time updates
-> site survey is collected
-> delivery company receives equipment list, layouts, and site context
-> equipment ships to installation company
-> delivery is scheduled after receipt
-> installation company sends completed-install photos and customer sign-off
-> sales rep attends install or follows up depending on order/customer importance
-> customer moves into relationship management
```

Target FAST OS loop:

```text
approval artifact arrives
-> FAST OS validates order-readiness context
-> FAST OS surfaces order readiness state and missing information
-> human approves handoff
-> FAST OS prepares invoice milestone and vendor PO packages
-> humans approve customer-facing financial documents and vendor commitments
-> FAST OS tracks vendor acknowledgments, lead times, payment status, and open blockers
-> FAST OS collects site survey and updates delivery readiness state
-> FAST OS keeps project manager and sales rep in sync
-> FAST OS prepares customer status updates for review or policy-bound sending
-> installation company submits completion evidence
-> FAST OS records completion, exceptions, installed assets, and relationship follow-up triggers
```

## Work Unit Inventory

| ID | Work Unit | Trigger | Decision | Required Context | Output | State Change | Risk If Wrong | AI Autonomy | Human Review | Confidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| CW-01 | Capture approval proof | Customer sends signed quote or PO | Is this a valid approval artifact? | Quote, signer/customer, PO/signed quote, terms, scope, version | ApprovalProof | Quote can move toward order readiness | High | Observe / prepare | Sales rep or order owner confirms | Evidence-backed |
| CW-01A | Validate PO against quote / highlight contract terms | Approval proof is a PO or customer contract terms are present | Does the PO match the accepted quote, and do any terms need human review? | PO, accepted quote version, line items, prices, quantities, bill-to/ship-to, payment terms, legal terms | PurchaseOrderReview / ContractReviewHighlight | Mismatches or non-standard terms are routed before order action | High | Compare / highlight | Project manager, sales, management, or contract owner | Evidence-backed / product implication |
| CW-02 | Validate order readiness | Approval proof captured | Is the sold scope complete enough to move forward operationally? | Quote version, line items, ship-to/install location, contacts, F&I, trade-in/extraction, flooring, layout requirement, custom details, terms, site context | OrderReadinessState / OrderReadinessChecklist | Opportunity marked ready / blocked | High | Prepare only | Sales rep and project manager | Evidence-backed / strong inference |
| CW-03 | Surface missing order-readiness context | Order readiness has missing or uncertain fields | Who needs to provide each missing fact, and when should FAST OS request it? | Missing field, owner, customer/internal source, due date, blocker/warn status | MissingInformationRequest / OrderBlocker | Required context is routed instead of buried in NetSuite or Outlook | Medium to high | Recommend / request with policy | Project manager by default; owner varies by field | Evidence-backed |
| CW-04 | Set payment terms and invoice milestones | Sales order / order handoff starts | What terms apply and what invoice should be sent first? | Customer terms, default 50/40/10, prepaid, Net terms, order value, policy | InvoiceMilestonePlan / DepositInvoiceDraft | Payment workflow starts | High | Prepare only | Accounting / order team | Evidence-backed |
| CW-05 | Create vendor purchase order package | Order handoff starts | Which vendors require POs and what should each PO include? | Quote lines, vendor, SKU, quantities, options, costs, ship-to, lead times | VendorPOPackage | Vendor procurement starts | High | Prepare with approval | Project manager / purchasing | Evidence-backed |
| CW-06 | Track vendor acknowledgments and lead times | POs sent | What timing should customer and team expect? | Vendor response, estimated lead times, payment status, order status | LeadTimeStatusUpdate | Project timeline updated | Medium | Observe / draft | Project manager | Evidence-backed |
| CW-07 | Send customer payment/status updates | Payment received or lead times received | What should the customer be told now? | Payment status, vendor lead times, schedule constraints, project stage | CustomerStatusUpdate | Customer informed; project confidence maintained | Medium to high | Draft / execute with policy approval | Project manager | Evidence-backed |
| CW-07A | Route relationship-sensitive operational decision | PM detects operational issue affecting customer cost, bad news, substitution, scope, or trust | Does the issue require sales relationship judgment before customer communication or project-cost decision? | Operational issue, customer impact, cost/margin impact, options, PM recommendation, account relationship context | SalesDecisionRequest / CustomerImpactDecision | Sales owns decision; PM can continue coordination after direction | Medium to high | Recommend / prepare | Sales rep decides customer-facing path; PM coordinates execution | Evidence-backed from Regency edge cases |
| CW-08 | Collect site survey | Order moves toward installation prep | Is the site ready for delivery and install? | Customer site survey, access, hours, elevator/loading, obstacles, power, floor protection, contacts | SiteSurvey | Install readiness context captured | Medium to high | Prepare / request with review | Project manager / customer | Evidence-backed |
| CW-09 | Assemble delivery/install readiness view or export | Site survey and order context available | What does the delivery/install team need to execute smoothly? | Equipment list, layouts, site survey, delivery path, install scope, customer contacts, constraints | DeliveryReadinessState / optional ReadinessExport | Delivery company receives install prep context when needed | High | Prepare with approval | Project manager / install coordinator | Evidence-backed |
| CW-10 | Track shipment to installation company | Vendor ships equipment | Has equipment arrived and is it complete enough to schedule? | Vendor tracking, dealer-provided equipment list, installer email confirmation, packing slip cross-check when available, receiving status, backorders, freight status, installer warehouse | ReceivingStatus / ReceivingConfirmation | Delivery scheduling becomes possible only after the delivery company / installer confirms readiness | Medium | Observe / recommend | Installer confirms receipt; project manager decides exceptions | Evidence-backed |
| CW-10A | Resolve backorder or substitution exception | Vendor lead time or backorder makes normal delivery path unacceptable | Should the project wait, split delivery, substitute, cancel, upgrade, use another vendor, or present another option? | Affected item, lead time, customer timing, substitute products, layout impact, price/margin impact, SO/PO revision need | SubstitutionDecision / BackorderResolution | Order scope and delivery readiness update | High | Prepare options / route decision | Sales rep owns customer choice; PM/purchasing updates order path | Evidence-backed from Regency edge case |
| CW-11 | Schedule delivery/install | Equipment received | When should installation happen and who must be coordinated? | Customer availability, installer availability, site readiness, received equipment, scope | InstallSchedule | Delivery/install date set | High | Recommend / prepare | Project manager and customer | Evidence-backed |
| CW-11A | Resolve non-standard extraction sequence | Trade-in/extraction must occur before new equipment delivery because of flooring or other site work | Who owns the extra trip, customer communication, installer schedule, and margin impact? | Trade-in line, related flooring quote status, flooring vendor dependency, extraction date, install date, installer trip charge, customer-cost decision | ExtractionSequenceDecision | Execution plan changes from single install flow to staged extraction and return install | High | Detect / prepare decision summary | Sales rep owns customer-cost decision; PM owns scheduling | Evidence-backed from Regency edge case |
| CW-12 | Keep sales rep in the loop | Project status changes | What does the rep need to know to manage the relationship? | Project stage, customer issues, delays, payment, install schedule, exceptions | RepVisibilityUpdate | Rep remains relationship-aware | Medium | Observe / draft | Project manager or rep | Evidence-backed |
| CW-13 | Capture install completion evidence | Install completed | Is the install complete and accepted? | Customer signature on delivery confirmation, install pictures, item list, notes, serial number fields when used, exceptions, punch list, completion date | InstallationCompletionPacket | Project can close, final invoice can be sent, and sales rep commission can move forward, or project moves to exceptions | High | Request / monitor / organize / prepare | Installer submits proof; PM validates | Evidence-backed |
| CW-14 | Handle install exceptions | Completion evidence has issues or installer reports damage / missing parts | Is anything incomplete, damaged, missing, rejected, or awaiting repair? | Photos, delivery confirmation notes, installer comments, customer concerns, missing-part notes, vendor response, order scope | Exception / PunchList / VendorRepairFollowUp | Project remains open until resolved; PM contacts vendor and installer returns for repair | High | Recommend / prepare / monitor | Project manager owns vendor follow-up; sales stays visible for relationship-sensitive issues | Evidence-backed |
| CW-15 | Start relationship management flow | Install complete and accepted | What follow-up cadence should begin? | Customer, installed equipment, project outcome, account value, rep ownership | RelationshipManagementTrigger | Account enters post-install cadence | Medium | Recommend / draft | Sales rep | Evidence-backed |

## Decision Inventory

| Decision | Where It Happens | Why It Matters | Who Validates It | Confidence |
| --- | --- | --- | --- | --- |
| Is the customer commitment valid? | Approval proof capture | A signed quote or customer PO is the threshold for order creation. | Sales rep / order owner | Evidence-backed |
| Is the sold scope complete enough to hand off? | Order readiness | Missing scope causes rework, wrong POs, customer confusion, or install problems. | Sales rep and project manager | Strong inference |
| Which payment terms apply? | Invoice milestone setup | 50/40/10, prepaid, and Net terms change invoice timing and cash-flow expectations. | Accounting / order team | Evidence-backed |
| How many vendor purchase orders are required? | Vendor PO package | Multi-vendor orders require multiple POs and separate lead-time tracking. | Purchasing / project manager | Evidence-backed |
| What status update should the customer receive? | Customer communication | Customer confidence depends on clear updates after payment and vendor lead-time confirmation. | Project manager | Evidence-backed |
| Does an operational issue require sales relationship judgment? | Operational exception routing | Customer-facing added cost, bad news, substitution, scope change, or margin absorption should be decided by the sales rep because the rep owns the relationship. | Sales rep | Evidence-backed from Regency edge cases |
| Is the site ready for delivery? | Site survey / delivery prep | Poor site readiness creates failed delivery, delays, damage, or install friction. | Project manager / install coordinator | Evidence-backed |
| Is the delivery team prepared? | Delivery readiness packet | Equipment lists, layouts, and site information reduce install surprises. | Project manager / installer | Evidence-backed |
| Is a trade-in extraction standard or staged? | Delivery/install planning | Trade-in usually implies extraction during install, but flooring or construction can require extraction before new equipment delivery and create an extra trip cost. | Sales rep for customer-cost decision; project manager for schedule | Evidence-backed from Regency edge case |
| Is a backorder acceptable or does it require substitution? | Vendor lead-time tracking | A long backorder can make the normal wait-for-all-items flow unacceptable and require customer choice. | Sales rep for customer-facing decision; PM for operational path | Evidence-backed from Regency edge case |
| Should the rep attend the install or follow up afterward? | Install completion / relationship continuity | The rep manages the relationship; larger or strategic customers may need rep presence. | Sales rep | Evidence-backed |
| Is the install complete and accepted? | Completion evidence capture | Customer signature on the delivery confirmation plus pictures determine closeout, final invoice readiness, commission timing, exceptions, and relationship transition. | Project manager validates; installer submits proof | Evidence-backed |

## Context Inventory

| Context Needed | Used By | Current Source | Reliability | Missing Pieces |
| --- | --- | --- | --- | --- |
| Approval artifact | Approval proof and handoff | Signed quote or customer PO | High when captured | Artifact type, signer, accepted version, date |
| Quote / sold scope | Order handoff, POs, delivery packet | Quote / sales order | High if locked | Revision history, exceptions, customer-facing exclusions |
| Payment terms | Deposit invoice and milestone plan | Customer/order terms | Medium | When and how terms are chosen; approval policy |
| Vendor split | PO package | Quote line vendors | High | Vendor-specific ordering rules and acknowledgments |
| Lead times | Customer updates and schedule planning | Vendor responses | Medium | Staleness, partial shipments, backorders |
| Deposit/payment status | Vendor ordering and order progress | Invoice/payment record, accounting update | Medium to high | Extended nonpayment follow-up owner and abandonment handling |
| Receiving confirmation | Install scheduling | Installer / delivery company email, dealer-provided equipment list, packing slip when available | Medium | Current document name, exact cross-check process, and how often false-ready receiving occurs |
| Relationship-sensitive issue context | Sales decision routing | PM update, customer email, vendor delay, cost impact | Medium | Clear threshold for notifying sales versus making information visible |
| Site survey | Install readiness | Customer-provided survey | Medium | Survey format, required fields, validation process |
| Equipment list | Delivery prep | Quote / order | High | Final model/options, substitutions, backorders |
| Related quote status | Order readiness and execution sequence | Quote records, customer approval state, email | Medium | Whether unapproved related scope still affects execution |
| Layouts | Delivery and install team | Design/proposal artifacts | Medium to high | Version control, whether layout is approved for install |
| Delivery company requirements | Delivery readiness | Project manager / installer | Needs research | Best-practice packet format |
| Install completion proof | Completion closeout | Installer photos and customer sign-off | High if linked | Exception notes, punch-list status |
| Rep relationship context | Rep visibility / post-install flow | Sales rep, CRM, project notes | Medium | When rep should intervene, follow-up cadence |

## Output And State Inventory

| Output Or State | Produced By | Used Later By | Data Object Or Event |
| --- | --- | --- | --- |
| Approval proof | Customer approval capture | Order readiness, audit, handoff | `ApprovalProof`, `CustomerCommitmentEvent` |
| PO / contract review | Approval capture | Order readiness and human review | `PurchaseOrderReview`, `ContractReviewHighlight` |
| Order readiness checklist | FAST OS / sales review | Handoff and blocker resolution | `OrderReadinessChecklist`, `OrderBlocker` |
| Order readiness state | FAST OS / PM review | Project manager, orders team | `OrderReadinessState`, `MissingInformationRequest` |
| Invoice milestone plan | Payment workflow setup | Accounting, project manager | `PaymentTerms`, `InvoiceMilestonePlan` |
| Deposit invoice draft / record | Accounting workflow | Customer, payment tracking | `Invoice`, `PaymentMilestone` |
| Vendor PO package | Procurement workflow | Vendors, project manager | `VendorPurchaseOrder`, `VendorOrder` |
| Lead-time status | Vendor response tracking | Customer updates, schedule planning | `LeadTimeStatus`, `VendorAcknowledgmentEvent` |
| Customer status update | PM/customer communication | Customer confidence and audit | `CustomerStatusUpdateEvent` |
| Site survey | Customer readiness capture | Delivery/install prep | `SiteSurvey`, `InstallReadinessInput` |
| Delivery readiness state / optional export | Install preparation | Delivery company / installer | `DeliveryReadinessState`, `ReadinessExport` |
| Receiving status | Shipment tracking and installer receipt confirmation | Install scheduling | `ReceivingEvent`, `ShipmentStatus`, `ReceivingConfirmation` |
| Install schedule | Delivery coordination | Customer, installer, rep | `InstallScheduleEvent` |
| Rep visibility update | Project status sync | Sales rep relationship management | `RepVisibilityEvent` |
| Installation completion packet | Install closeout | Project closeout, final invoice, commission timing, relationship flow | `InstallationCompletionPacket`, `DeliveryConfirmation`, `CompletionPhotoSet` |
| Relationship management trigger | Post-install transition | Sales rep / account management | `RelationshipFollowUpPlan`, `InstalledBaseLifecycleTrigger` |

## Risk And Autonomy Matrix

| Work Unit | Risk If Wrong | Recommended AI Role | Human Approval Required? | Notes |
| --- | --- | --- | --- | --- |
| Capture approval proof | High | Observe / prepare | Yes | FAST OS can identify likely approval, but humans confirm commitment. |
| Validate PO / highlight contract terms | High | Compare and highlight | Yes | PO mismatch and non-standard terms require human review. |
| Validate order readiness | High | Prepare checklist | Yes | Missing context can break procurement or install. |
| Surface missing order-readiness context | Medium to high | Route missing facts and draft requests | Review depends on field | PM usually owns collection; field owner varies. |
| Set payment terms and invoice milestones | High | Prepare only | Yes | Financial terms require policy/accounting control. |
| Create vendor PO package | High | Prepare with approval | Yes | Vendor financial commitments should not be autonomous early. |
| Track vendor acknowledgments and lead times | Medium | Observe / draft | Usually no for internal updates; yes for customer promises | Lead time promises are trust-sensitive. |
| Send customer status updates | Medium to high | Draft / policy-bound send | Yes initially | Customer communication should be reviewed until tone/policy are proven. |
| Collect site survey | Medium | Prepare / request | Review recommended | Survey can be automated but should be validated for completeness. |
| Assemble delivery/install readiness view or export | High | Prepare with review | Yes | Delivery errors are expensive and visible; packet export is optional. |
| Track shipment to installation company | Medium | Observe / recommend | No for tracking; yes for escalation | Good automation target. |
| Schedule delivery/install | High | Recommend / prepare | Yes | Requires customer and installer coordination. |
| Keep sales rep in the loop | Medium | Observe / draft | No for internal visibility; yes for customer-sensitive escalations | Core FAST OS value because rep owns relationship. |
| Capture install completion evidence | High | Request / monitor / prepare | Yes | Completion proof collection is a pain point; missing signature or pictures can delay final invoice and commission. |
| Start relationship management flow | Medium | Recommend / draft | Rep review | Follow-up should preserve relationship tone. |

## Capability Implications

| Capability Candidate | Supported Work Units | User Value | Dependencies | Confidence |
| --- | --- | --- | --- | --- |
| Quote-to-order readiness | CW-01, CW-02, CW-03 | Prevents messy handoffs and lost project context after approval. | Quote, approval proof, site/project context, review records | Strong inference |
| Order handoff assistant | CW-03, CW-04, CW-05 | Turns closed-won approval into complete operations packet without rep retyping. | Quote data, payment terms, vendor/product mapping, audit | Strong inference |
| Vendor procurement coordinator | CW-05, CW-06, CW-10 | Tracks multi-vendor POs, acknowledgments, lead times, and receiving status. | Vendor records, PO events, shipment tracking | Strong inference |
| Customer status update assistant | CW-06, CW-07, CW-11 | Keeps customers informed without requiring PMs to manually reconstruct status. | Payment status, lead times, schedule, communication policy | Evidence-backed / strong inference |
| Install readiness assistant | CW-08, CW-09, CW-11 | Reduces delivery surprises by collecting site survey and assembling prep packet. | Site survey, layouts, equipment list, installer requirements | Evidence-backed / strong inference |
| Rep visibility and relationship continuity | CW-12, CW-15 | Keeps the rep in the loop because the rep manages the relationship. | Project events, customer importance, account ownership, follow-up rules | Evidence-backed |
| Install completion and closeout capture | CW-13, CW-14, CW-15 | Links delivery confirmation, customer signature, pictures, exceptions, final invoice readiness, commission timing, and relationship follow-up. | Installer submissions, customer sign-off, completion photos, punch list, installed base | Evidence-backed |

## Schema Implications

| Object / Event / Artifact | Why It Is Needed | Source / Provenance Need | Review / Audit Need |
| --- | --- | --- | --- |
| `ApprovalProof` | Records signed quote or PO threshold for order creation. | Link to signed quote, PO, email, signer, date, quote version. | Human confirmation required. |
| `CustomerCommitmentEvent` | Marks the business event that moves sales into order coordination. | Customer-provided artifact and accepted terms. | Audit event. |
| `OrderReadinessChecklist` | Prevents closed-won handoff with missing information. | Quote, site, payment, vendor, install context. | Sales/PM review. |
| `OrderBlocker` | Makes missing handoff information explicit. | Source of missingness and owner. | Resolution audit. |
| `OrderReadinessState` | Packages validated sales, quote, customer, site, custom-detail, F&I, and delivery context as FAST OS state. | Quote, notes, site survey, layouts, customer context, source systems. | Human review. |
| `PurchaseOrderReview` | Compares customer PO against accepted quote. | PO, quote, line items, terms, bill-to/ship-to. | Human review for mismatches. |
| `ContractReviewHighlight` | Highlights customer contract/PO terms needing review. | PO/contract source and extracted term. | Human review. |
| `PaymentTerms` | Supports 50/40/10, prepaid, Net terms, and future terms. | Customer/account policy and deal terms. | Accounting review. |
| `InvoiceMilestonePlan` | Tracks deposit, progress, and final invoice timing. | Terms, order stage, payment status. | Accounting audit. |
| `VendorPurchaseOrder` | Models one PO per vendor where needed. | Quote lines, vendor source, cost/source version. | Purchasing approval. |
| `VendorAcknowledgmentEvent` | Tracks vendor confirmation and lead time. | Vendor response. | Needed for customer promise provenance. |
| `LeadTimeStatus` | Feeds project schedule and customer updates. | Vendor / shipment source. | Staleness and revision tracking. |
| `CustomerStatusUpdateEvent` | Records customer communications. | PM/agent draft, sent message, source facts. | Review and audit. |
| `SiteSurvey` | Captures customer-provided delivery/install constraints. | Customer response and validation status. | PM/installer review. |
| `DeliveryReadinessState` | Provides delivery company with equipment list, layouts, and site facts. | Quote, layout, site survey, contacts. | Review before release. |
| `ReadinessExport` | Optional vendor/installer/customer/accounting-facing packet or PDF generated from readiness state. | FAST OS readiness state and source links. | Review before external release. |
| `ReceivingEvent` | Tracks equipment receipt at installation company. | Installer/warehouse/vendor update. | Exception tracking. |
| `InstallScheduleEvent` | Records scheduled installation date/time and participants. | Customer and installer confirmation. | Customer-facing approval. |
| `InstallationCompletionPacket` | Captures completed install pictures, customer signature, delivery confirmation, notes, and completion date. | Installer submission and customer signature. | PM validation. |
| `PunchListItem` | Tracks incomplete/damaged/missing work after install. | Photos, installer notes, customer notes, delivery confirmation notes. | Resolution audit. |
| `CompletionProofRequest` | Tracks request, reminder, receipt, and review of installer-submitted completion proof. | PM request, installer email/upload, pictures, delivery confirmation. | Blocks completion until resolved or explicitly overridden. |
| `RepVisibilityEvent` | Keeps sales rep aware of important project milestones. | Project status event and reason. | Internal audit optional. |
| `RelationshipFollowUpPlan` | Starts post-install relationship management. | Account, installed assets, project outcome, rep ownership. | Rep review. |

## Emerging Agent Candidate Clusters

Do not treat these as final agent names. They are candidate clusters emerging from repeated work units.

| Candidate Cluster | Work Units Included | Shared Context / Tools | Autonomy Boundary | Validation Needed |
| --- | --- | --- | --- | --- |
| Approval and handoff readiness cluster | CW-01, CW-02, CW-03 | Quote, approval proof, order context, site/project context | Prepare checklists and packets; human approves handoff | Validate what PMs actually need at handoff. |
| Procurement coordination cluster | CW-04, CW-05, CW-06, CW-10 | Payment terms, vendor POs, acknowledgments, lead times, shipments | Track and draft; financial/vendor commitments require approval | Research back-office best practices and purchasing workflow. |
| Install readiness cluster | CW-08, CW-09, CW-11 | Site survey, layouts, equipment list, installer requirements, schedule | Prepare packets and recommend scheduling; human confirms | Collect real site survey and installer packet examples. |
| Customer communication cluster | CW-07, CW-12, CW-15 | Project status, payment, lead times, schedule, rep ownership | Draft updates; policy-bound sends only after trust is proven | Define communication policy and escalation rules. |
| Completion and relationship continuity cluster | CW-13, CW-14, CW-15 | Completion photos, sign-off, punch list, installed base, account follow-up | Capture and recommend; humans validate exceptions and relationship actions | Validate post-install cadence and installed-base handoff. |

## Best-Practice Research Needed

Josh has limited visibility into detailed back-office order, purchasing, accounting, and logistics processes. Before turning this into an implementation spec, supplement with research and/or interviews on:

- commercial equipment dealer order management best practices
- deposit and milestone invoice workflows
- multi-vendor purchase order coordination
- vendor acknowledgment and lead-time tracking
- warehouse / installer receiving workflows
- site survey requirements for delivery and installation
- delivery readiness view / optional packet contents
- install completion evidence standards
- punch-list / exception handling
- customer status update cadence
- sales-to-project-management handoff patterns
- rep visibility rules when the project manager owns execution but the rep owns the relationship

## Validation Status

Active cross-artifact questions now live in:

[Open Question Register v1](open-question-register-v1.md)

This workflow remains a strong first-pass decomposition. The main unresolved areas are:

- order/execution readiness completeness
- site survey field validation
- installer / delivery readiness validation
- payment milestone detail
- project status events that should notify the sales rep
- post-install relationship-management cadence

Do not duplicate the full question list here. Use the register to decide what to ask next.

## Synthesis Notes

| Type | Note |
| --- | --- |
| Observed fact | A quote should become closed won only after a signed quote or customer PO is received. |
| Observed fact | Once closed won, the current workflow creates a sales order and sends it to the orders team. |
| Observed fact | Current new order notes are often reminders for the project manager because the information already exists elsewhere in the system. |
| Observed fact | Deposit invoice creation depends on terms; 50/40/10 is common, but prepaid and Net terms also exist. |
| Observed fact | Multi-vendor orders require multiple purchase orders. |
| Observed fact | Project managers update customers after payment is received and vendor lead times are available. |
| Observed fact | Site surveys, equipment lists, and layouts help prepare the installation team. |
| Observed fact | Equipment is shipped to the installation company, and delivery is scheduled after equipment is received. |
| Observed fact | Installation company completion photos and customer sign-off are part of closeout evidence. |
| Observed fact | The sales rep must stay in the loop because the rep manages the relationship, even when the project manager owns scheduling and planning. |
| Inference | FAST OS can improve dealer profitability by letting project managers oversee more projects through automation of mechanical coordination tasks. |
| Inference | Delivery/install is relationship-sensitive and execution-sensitive, so it needs human-in-the-loop review even where preparation and tracking are automated. |
| Product implication | FAST OS should treat order handoff, payment/vendor coordination, install readiness, completion evidence, and relationship continuity as one connected post-close workflow. |
| Schema implication | The post-close workflow requires explicit approval, handoff, payment, PO, site survey, delivery readiness, receiving, install schedule, completion, exception, and relationship-follow-up objects/events. |
| Josh validation needed | Detailed back-office process should be supplemented with research and interviews before implementation decisions are made. |
