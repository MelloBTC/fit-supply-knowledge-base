---
title: Sales
type: Index
domain: sales
knowledge_scope: target-state
status: Draft
last_reviewed:
reviewed_by:
sources:
  - schema.md
  - PROJECT_CONTEXT.md
  - raw/imports/fast-os-capability-roadmap-source-inventory.md
  - wiki/sales/hunter-sales-existing-multifamily-pattern.md
  - wiki/sales/freight-install-quote-readiness.md
  - wiki/sales/proposal-package-readiness.md
  - wiki/order-execution/index.md
related:
  - [[../index|Fit Supply Knowledge Base Index]]
  - [[../governance/index|Governance]]
  - [[../order-execution/index|Order Execution]]
  - [[source-aware-lead-intake-routing|Source-Aware Lead Intake And Routing]]
  - [[lead-to-closed-won-workflow|Lead To Closed Won Workflow]]
  - [[hunter-sales-existing-multifamily-pattern|Hunter Sales Existing Multifamily Pattern]]
  - [[freight-install-quote-readiness|Freight And Install Quote Readiness]]
  - [[proposal-package-readiness|Proposal Package Readiness]]
agent_answerability:
  - What belongs in the Sales domain?
  - Which starter pages should be created first for this domain?
tags:
  - domain-index
  - sales
provenance_notes: Starter domain index created during target-state skeleton setup; updated 2026-06-27 to reflect the hunter-sales validation-status checkpoint, source-aware lead-intake example-first outcome capture, freight/install quote-readiness synthesis, proposal package readiness synthesis, and order-execution pilot migration.
---

# Sales

Sales knowledge connects customer needs, qualification, quoting, proposals, financing, and sales handoffs to the target-state distributor operating model.

## Focus Areas

- Lead qualification
- Customer types and personas
- Quoting and proposal workflows
- Financing and purchasing patterns
- Sales to project handoff
- Agent-assisted sales workflows

## Current Pages

- [[source-aware-lead-intake-routing|Source-Aware Lead Intake And Routing]]
- [[lead-to-closed-won-workflow|Lead To Closed Won Workflow]]
- [[hunter-sales-existing-multifamily-pattern|Hunter Sales Existing Multifamily Pattern]]
- [[freight-install-quote-readiness|Freight And Install Quote Readiness]]
- [[proposal-package-readiness|Proposal Package Readiness]]

## Active Lanes

`source-intelligence` and `lead-intake` are active sales sub-lanes for preserving lead source events, classifying source type, routing first workflow, assigning reviewed action, and tracking outcomes. The current page now includes a Bailey formal-feed curation example and a Park service-created replacement source-to-quote/no-response outcome example. Keep these inside `sales` for now. Do not promote a top-level `lead-intelligence` domain until more validated compiled pages create enough repeated navigation or ownership pressure.

`hunter-sales` is an active sales sub-lane for target discovery, prospecting policy, reactivation, nurture, and human-reviewed outreach. Keep it inside `sales` for now. The current validation-status checkpoint strengthens source-origin routing, service-to-sales replacement signals, grouped-property review, and active-workflow duplicate blocking. A dealer-backed Regency capture now anchors the active-workflow duplicate-block guardrail after outbound response, site visit, proposal, bid collection, approved quote, and closed-won states. A soft-negative split-candidate capture clarifies that negative replies need classification before hard suppression, but budget-window, no-response, manager-change, hard-stop scope, soft-negative, and sensitive-account rules still remain provisional until dealer examples validate them. Do not promote a top-level `lead-intelligence` or `prospecting` domain until validated pages create enough repeated navigation or ownership pressure.

`quote-readiness` is now an active sales sub-lane for customer-facing quote completeness, especially freight, install, and extraction/removal assumptions. Keep [[freight-install-quote-readiness|Freight And Install Quote Readiness]] inside `sales` while linking it to `order-execution`, `governance`, and `equipment`.

`proposal-readiness` is now an active sales sub-lane for customer-facing proposal package completeness, especially project context, room uncertainty, design assets, visual review, quote/package alignment, delivery event, and follow-up state. Keep [[proposal-package-readiness|Proposal Package Readiness]] inside `sales` while linking it to `design`, `projects`, `order-execution`, and `governance`. Do not promote a top-level `quote-readiness`, `pricing`, `proposal-readiness`, or `freight-install` domain until quote/proposal readiness pages multiply beyond the current F&I and proposal package pages.

## Starter Pages To Add

- `lead-qualification.md`
- `customer-types.md`
- `quote-workflow.md`
- `sales-agent-answerability.md`

## Maintenance Notes

- Check this index before creating new pages in this domain.
- Keep claims source-backed and link to related domains when workflows cross boundaries.
- Leave new pages in Draft until reviewed.
