---
title: Commercial Fitness Distributor Operating Model
type: Concept
domain: company
knowledge_scope: target-state
status: Draft
last_reviewed:
reviewed_by:
sources:
  - raw/imports/fast-os-capability-roadmap-source-inventory.md#fscr-002
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/05-capability-roadmap/commercial-fitness-dealer-operating-model-v1.md
related:
  - [[../knowledge-base/distributor-workflow-map|Distributor Workflow Map]]
  - [[../knowledge-base/agent-capability-map|Agent Capability Map]]
  - [[../sales/lead-to-closed-won-workflow|Lead To Closed Won Workflow]]
  - [[../order-execution/index|Order Execution]]
  - [[../order-execution/close-won-to-delivery-workflow|Close Won To Delivery Workflow]]
agent_answerability:
  - What is the target-state operating model for a commercial fitness equipment distributor?
  - Which lifecycle stages should future workflow and agent pages map back to?
  - Which data object families need to persist across sales, design, order-execution, service, and relationship growth?
tags:
  - operating-model
  - distributor-lifecycle
  - roadmap-derived
provenance_notes: Synthesized from FSCR-002 as target-state design. This is not a claim about current Fit Supply operations. Updated 2026-06-27 after order-execution became the first promoted workflow domain.
---

# Commercial Fitness Distributor Operating Model

This page defines the target-state operating model this wiki should use when organizing commercial fitness distributor knowledge. It uses Fit Supply as the concrete example business, but it should not be read as a current-state description of exactly how Fit Supply works today.

## Operating Thesis

A commercial fitness equipment distributor needs to turn demand into completed, supported customer outcomes:

```text
find qualified demand
-> win profitable equipment projects
-> deliver and install the right solution
-> support the customer after the sale
-> use installed-base and relationship context to grow future revenue
```

For FAST OS and this wiki, the simpler working frame is:

```text
find demand -> make it actionable -> convert it into a project -> execute the project -> preserve the account relationship
```

The first product wedge can stay sales-first, but the knowledge model cannot stop at the quote. Quote, approval, order readiness, delivery, install, service, and relationship continuity all depend on context created earlier in the lifecycle.

## Lifecycle Spine

| Stage | Business Question | Primary Wiki Domains | Target-State Knowledge Needed |
| --- | --- | --- | --- |
| 1. Market and account intelligence | Where should attention go before a lead appears? | `sales`, `company` | Account segments, territories, properties, installed-base signals, ownership/management changes, budget timing, and demand indicators. |
| 2. Lead source ingestion | How does possible demand enter the business? | `sales`, `knowledge-base` | Source events, source provenance, dedupe, lead signals, and source-quality learning. |
| 3. Lead qualification and outreach | Which leads are worth action and what should the rep do next? | `sales` | Qualification state, research needs, outreach angle, follow-up, and disqualification reasons. |
| 4. Opportunity and buyer discovery | Is this a real project and who has to be convinced? | `sales`, `company` | Buyer roles, budget signals, timeline, procurement path, facility type, and stakeholder motivation. |
| 5. Site, room, and project context capture | What must be true about the space before design, quote, or install? | `design`, `projects`, `equipment` | Site, room, measurements, photos, constraints, access, existing equipment, and customer goals. |
| 6. Solution design and product selection | What equipment solution fits the customer, space, budget, timeline, and distributor strategy? | `design`, `equipment`, `sales` | Layouts, product options, manufacturer fit, warranty/availability, substitutes, and product-selection rationale. |
| 7. Quote, pricing, margin, and proposal | Can the solution become an accurate, profitable, persuasive offer? | `sales`, `equipment`, `governance` | Quote lines, pricing provenance, freight/install estimates, tax, margin, terms, proposal assets, and review events. |
| 8. Close, approval, and quote-to-order handoff | What happens when the customer says yes, and what must not be lost? | `sales`, `order-execution` | Approval proof, accepted quote version, PO or signed quote, handoff checklist, order-readiness input, and customer confirmation. |
| 9. Procurement, vendor, freight, and order coordination | How does the right equipment get ordered, confirmed, shipped, and tracked? | `order-execution` | Vendor POs, acknowledgments, lead times, shipment status, payment milestones, customer updates, and exceptions. |
| 10. Delivery, installation, and project completion | How does the equipment arrive, get installed, and become a completed customer outcome? | `order-execution`, `service` | Site readiness, delivery constraints, installer schedule, punch list, completion photos, signoff, and installed-product records. |
| 11. Warranty, service, preventive maintenance, and installed-base lifecycle | How does sold equipment become durable account knowledge? | `service`, `equipment` | Installed assets, serials, warranty, service requests, work orders, PM schedules, lifecycle status, and replacement triggers. |
| 12. Account expansion, renewal, replacement, and future demand | How does completed work create future revenue? | `sales`, `service`, `company` | Lifecycle signals, service history, satisfaction, replacement opportunities, referrals, and relationship memory. |

Real workflows loop backward. A site visit can change qualification. Layout can change equipment selection. Quote revisions can reopen discovery. Install issues can create service work or future sales.

## Role Map

| Role | Primary Goal | Wiki Design Implication |
| --- | --- | --- |
| Owner-operator | Grow revenue, protect margin, avoid missed opportunities, and see business health. | Visibility should emerge from workflow state, not extra reporting chores. |
| Sales manager | Route leads, coach reps, review pipeline, and unblock stuck opportunities. | Manager views need trustworthy workflow signals and source-backed state. |
| Sales rep | Find opportunities, build relationships, win projects, and avoid admin drag. | Rep utility must come before management reporting. |
| Designer or layout support | Convert goals and constraints into a workable facility solution. | Design artifacts must stay linked to quote, proposal, product, and install context. |
| Operations coordinator or project manager | Move accepted projects through payment, vendors, freight, delivery, install, warranty, and updates. | Operations needs clean handoff data, not manual reconstruction from sales artifacts. |
| Service manager or technician | Keep installed equipment working and record lifecycle context. | Installed assets should become first-class knowledge, not forgotten quote lines. |
| Customer stakeholder | Get the right facility solution on time, on budget, and with minimal confusion. | Customer-facing output needs clarity, review, and timely status communication. |

## Data Object Spine

This is not a database schema. It is the cross-domain object spine future wiki pages and agent requirements should preserve.

| Layer | Candidate Objects | Why It Matters |
| --- | --- | --- |
| Business identity | Dealer, tenant, user, role, permission, team, territory. | Establishes ownership, access, routing, and trust boundaries. |
| Customer universe | Account, organization, location, property, site, contact, buyer role, management company. | Commercial fitness opportunities are location and stakeholder driven. |
| Demand signals | Lead source, lead signal, project, source event, RFP/bid event, referral, account trigger. | Future agents need to find and route demand before quoting begins. |
| Sales workflow | Lead, opportunity, interaction, task, qualification status, follow-up, stakeholder map. | Makes rep work actionable and visible without generic CRM busywork. |
| Site and solution | Site context, room, measurement, photo, drawing, constraint, layout, solution package. | Connects discovery, design, quote, proposal, delivery, and install. |
| Product and pricing | Product, manufacturer, SKU, category, option, warranty, price list, dealer cost, freight, install estimate, tax, margin rule. | Multi-manufacturer quoting depends on trusted product and pricing data. |
| Quote and proposal | Quote, quote version, quote line item, proposal, approval event, proposal send/view event. | Quote/proposal is where sales value, pricing trust, and handoff quality meet. |
| Order and fulfillment | Accepted quote, sales order, vendor PO, shipment, delivery window, install job, exception. | Prevents the sale from becoming manual reconstruction after close. |
| Installed base | Installed asset, serial number, warranty, service request, work order, PM schedule, replacement trigger. | Enables service, support, lifecycle intelligence, and expansion. |
| Trust and automation | Source, suggestion, confidence, review event, agent run, audit event, memory. | Required for AI-native work around customer, financial, and operational data. |

## Cross-Cutting Foundations

- Tenant and permission boundaries: customer, quote, memory, retrieval, and workflow data must not cross account or dealer boundaries.
- AI provenance and human review: suggestions around leads, quotes, pricing, customer records, and outreach need sources and review state.
- Activity capture: owner and manager visibility should emerge from real workflow activity without rep busywork.
- Source-aware records: lead, quote, customer, and AI-generated context should preserve where the information came from.
- Workflow state: the system needs to know stage, owner, next action, blocker, and due date.

## Validation Posture

This operating model is a useful parent map, but several assumptions still need direct validation before becoming product rules:

- Lead generation and actionable outreach appear to be the strongest first wedge, but formal validation is still needed.
- Quote/proposal remains a high-value conversion point, but it may not be the first daily rep hook.
- Installed-base data should be modeled early, but surfacing it too early could distract from sales adoption.
- Product and pricing normalization are foundational, but the commercial equipment knowledge-layer work belongs upstream in `fast-os-knowledge-base` until mature.
- Site and room context likely affect quoting quality, but some quick-quote flows may need a lighter path.
- AI should assist before it executes, with explicit provenance, permission, and review boundaries.

## Wiki Use

Use this page as the parent map when deciding where new pages belong. Domain pages should make their lifecycle position explicit and should link back to this operating model when their scope crosses sales, design, order-execution, projects, equipment, service, or governance.
