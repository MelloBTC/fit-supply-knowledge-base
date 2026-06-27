---
title: Hunter Sales Existing Multifamily Pattern
type: Workflow
domain: sales
knowledge_scope: design-hypothesis
status: Draft
last_reviewed:
reviewed_by:
sources:
  - raw/imports/fast-os-capability-roadmap-source-inventory.md#fscr-012
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/06-agent-workflow-decomposition/hunter-sales-target-discovery-and-coverage-workflow-decomposition-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/06-agent-workflow-decomposition/hunter-sales-policy-validation-matrix-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/06-agent-workflow-decomposition/hunter-sales-existing-multifamily-segment-policy-validation-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/06-agent-workflow-decomposition/hunter-sales-existing-multifamily-policy-profile-and-synthetic-scenarios-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/06-agent-workflow-decomposition/hunter-sales-existing-multifamily-real-example-policy-pressure-test-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/05-capability-roadmap/regency-at-dell-ranch-outbound-campaign-response-case-study-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/06-agent-workflow-decomposition/regency-lead-to-closed-won-work-unit-decomposition-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/06-agent-workflow-decomposition/hunter-sales-existing-multifamily-provisional-example-validation-pass-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/06-agent-workflow-decomposition/hunter-sales-existing-multifamily-provisional-sanitized-example-probes-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/06-agent-workflow-decomposition/hunter-sales-existing-multifamily-provisional-probe-validation-results-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/docs/06-agent-workflow-decomposition/hunter-sales-existing-multifamily-provisional-example-reasoning-notes-v1.md
  - C:/Users/joshm/projects/fast-os-capability-roadmap/fixtures/hunter-sales-existing-multifamily-policy-evaluator-v1/README.md
related:
  - [[lead-to-closed-won-workflow|Lead To Closed Won Workflow]]
  - [[../knowledge-base/distributor-workflow-map|Distributor Workflow Map]]
  - [[../knowledge-base/agent-capability-map|Agent Capability Map]]
  - [[../knowledge-base/domain-model-review|Domain Model Review]]
agent_answerability:
  - How should a target-state sales agent handle dormant or lightly covered existing multifamily targets?
  - Which prospecting actions can FAST OS prepare, queue, block, or recommend before rep review?
  - Which hunter-sales policy defaults are still candidate-only and require dealer validation?
tags:
  - hunter-sales
  - prospecting
  - existing-multifamily
  - policy-validation
  - roadmap-derived
provenance_notes: Synthesized from roadmap FSCR-012 as a design-hypothesis sales pattern. Updated 2026-06-27 with a validation-status checkpoint from real/sanitized example pressure tests, provisional probe results, a soft-negative split-candidate capture, and a dealer-backed Regency active-workflow duplicate-block example. The source family includes candidate policy defaults and synthetic fixture labels, so this page must not be treated as approved dealer policy, current Fit Supply operations, or build-ready evaluator behavior.
---

# Hunter Sales Existing Multifamily Pattern

This page captures a target-state pattern for hunter sales coverage of existing multifamily targets.

The pattern is intentionally labeled `design-hypothesis`. It is useful enough to guide wiki answerability, but the source family repeatedly treats the policy defaults, synthetic scenarios, cadence, and guardrail settings as candidate material that still needs dealer validation.

## Business Outcome

Bring the right dormant, lightly covered, or signal-triggered existing multifamily targets back into rep review at the right moment, with enough context for a relationship-safe decision.

```text
target universe and source coverage
-> dormant or lightly covered target
-> reactivation window or pursuit signal
-> account and buyer-path refresh
-> policy guardrail check
-> rep review package
-> pursue, nurture, deprioritize, suppress, retire, or convert
-> outcome learning recommendation
```

This is not a generic "send more email" workflow. The first durable product layer is target coverage, signal detection, reviewable pursuit briefs, human-reviewed outreach, response conversion, and learning.

## Source Boundary

FSCR-012 is a source family, not one stable finished policy document. It includes workflow decomposition, policy validation, existing multifamily segment pressure tests, candidate policy-profile shape, synthetic scenarios, evaluator fixture notes, and provisional validation labels.

This page does not import the machine-readable fixture bundle into the Fit Supply wiki. Fixture JSON and evaluator runner details should remain upstream unless this repo intentionally opens an evaluation-discipline lane.

## Core Pattern

| Principle | Meaning For The Wiki |
| --- | --- |
| Target account is broader than lead or opportunity. | FAST OS may track properties that are worth coverage before there is an active buying conversation. |
| Review trigger is not send trigger. | Budget windows, manager changes, property changes, service signals, and amenity clues should create review packages, not automatic customer-facing outreach. |
| Policy is data, not prompt text. | Cadence, sender identity, channels, suppression rules, approvals, stop rules, and learning thresholds belong in a `DealerProspectingPolicyProfile`. |
| Segment defaults are not universal. | Existing multifamily can have candidate defaults without forcing the same buyer path or cadence onto schools, new construction, hospitality, or other segments. |
| Learning recommends; policy approves. | Outcomes may recommend source, play, cadence, or segment-policy changes, but FAST OS should not silently rewrite dealer policy. |
| Audit is part of autonomy. | Queued, blocked, approved, rejected, overridden, or suppressed actions need policy version, actor, reason, evidence, and timestamp. |

## Work Unit Groups

| Group | Recurring Question | Target-State Output | AI Posture | Human Boundary |
| --- | --- | --- | --- | --- |
| Target coverage | Which segments, territories, sources, and account types should be monitored? | `TargetUniverseDefinition`, candidate target pool, source search run. | Search, classify, stage, and explain source confidence. | Dealer or rep confirms coverage policy and uncertain matches. |
| Account refresh | What changed about the property, management path, amenity, or account history? | `AccountResearchSnapshot`, source evidence, buyer-path hypothesis. | Refresh low-risk public facts with provenance; stage uncertain facts. | Rep reviews relationship notes, ambiguous conflicts, and sensitive fields. |
| Reactivation signal | What makes this target worth renewed attention now? | `ReactivationTrigger`, `PursuitSignal`, research refresh task. | Monitor approved sources and explain why review is suggested. | Rep confirms whether the signal deserves pursuit. |
| Treatment classification | Should this target be pursued, nurtured, deprioritized, retired, or suppressed? | `TargetTreatmentDecision`, suppression or nurture state. | Recommend treatment and enforce hard suppressions when policy-confirmed. | Rep, sales leadership, or policy owner handles soft and relationship-sensitive decisions. |
| Buyer path | Who likely influences or controls the equipment decision for this stage? | `BuyerPathHypothesis`, contact priority list. | Research and rank likely paths with confidence. | Rep chooses the outreach path and relationship angle. |
| Review package | What does the rep need to decide quickly and safely? | `PursuitBrief`, outreach draft, call task, review queue item. | Prepare concise context, draft only, and show guardrail results. | Rep approves customer-facing action. |
| Cadence guardrails | How should touches be spaced, stopped, or routed? | `CadenceGuardrail`, stop-rule check, approval requirement. | Apply approved policy and block or queue exceptions. | Dealer policy controls cadence, channels, sender identity, and override authority. |
| Learning loop | Which sources, plays, contacts, and outcomes improved or weakened pursuit quality? | `PursuitLearningEvent`, policy learning recommendation. | Analyze outcomes and recommend policy changes. | Dealer validates changes before policy mutates. |

## Existing Multifamily Policy Shape

The existing multifamily segment is a strong first validation slice because it has a concrete timing example, repeated account-change signals, clear suppression risks, and an obvious human relationship boundary.

Candidate review triggers include:

- June through August budget-season review for existing multifamily targets.
- Manager or management-company change.
- Property sale or ownership change.
- Fitness-specific amenity refresh clue.
- Aging equipment or recurring service issue.
- Reply, quote request, service-created replacement signal, or other source-origin event that should route into a downstream workflow.

Candidate low-effort or guarded states include:

- `hard_suppressed` for explicit do-not-contact, outside territory, property closed, or other policy-defined hard stop.
- `retired` for duplicate, nonexistent, permanent mismatch, or confirmed no-future-value targets.
- `deprioritized` for weak fit, bad contact data, recent competitor project, bad payment history, poor relationship, or strategic sensitivity.
- `long_tail_nurture` when timing may change later but current effort should stay low.
- `active_reactivation_review` when a window or signal justifies refreshed context and rep review.
- `opportunity_conversion_review`, `inbound_quote_readiness_review`, or `service_to_sales_review` when the signal is closer to active demand than ordinary prospecting.

## Human Review And Autonomy

Safe automatic work should stay internal: source monitoring, candidate staging, low-risk fact refresh with provenance, internal task creation, hard suppression enforcement when policy-confirmed, and outcome measurement.

Prepared-for-review work can include pursuit assessments, buyer-path hypotheses, review packages, cadence plans, outreach drafts, suppression recommendations, and conversion packages.

Explicit rep approval is required before customer-facing outreach, relationship-sensitive follow-up, opportunity conversion, or any action where tone, timing, sender identity, or account history could damage trust.

Dealer-level policy is required for territory coverage, source access, cadence defaults, channel rules, sender identity, hard stops, suppression overrides, learning thresholds, permissions, and audit requirements.

The v1 position is clear: automatic customer-facing outreach is not the default.

## Evaluation And Fixture Boundary

The roadmap source includes synthetic EMF-PRO scenarios and a fixture bundle. Those fixtures are useful for future evaluator discipline, but many scenarios remain `provisional_synthetic_candidate` or candidate defaults for validation.

The wiki should preserve this distinction:

- Real or sanitized examples can promote, split, or correct scenario expectations.
- Synthetic-only cases must stay visibly provisional.
- Fixture answer keys should not be treated as dealer-approved policy.
- A future evaluator should produce decision packages with evidence, guardrail results, required reviews, blocked actions, prepared artifacts, and learning signals.

## Validation Checkpoint - 2026-06-27

The next smallest durable checkpoint after FSCR-013 is a hunter-sales validation-status pass, not a build-readiness handoff.

The roadmap source family now includes real/sanitized pressure tests and provisional probe validation results. Those sources strengthen the pattern, but they do not promote the page out of `design-hypothesis` and do not make the fixture bundle dealer-approved.

### Real/Sanitized Example Read

| Example Evidence | What It Validates | What It Does Not Validate |
| --- | --- | --- |
| Regency outbound campaign response became site visit, proposal, approved quote, closed-won, and active workflow. | Approved outreach can convert to opportunity review; active proposal, bid, closed-won, order-readiness, or delivery/install states should block duplicate hunter outreach. | It does not prove budget-window reactivation, prospecting no-response thresholds, manager-change timing, or sensitive-account policy. |
| Lenox Park direct inbound bid request asked for specific equipment. | A high-intent quote request can originate outside an approved outbound sequence and should preserve `source_origin` before routing. | It does not validate manager-change reactivation, because the manager context belongs to an inbound quote request. |
| Park at Rialto service-created replacement signal became quote work. | Service or installed-base replacement demand needs service-to-sales review, replacement opportunity context, and quote-readiness preparation. | Its post-quote silence should not be reused as proof for pre-opportunity prospecting no-response policy. |
| Regency and Madison shared relationship context but stayed separate workflows. | Related-property or shared-management context should produce grouped review and relationship awareness without merging quotes, approvals, or outcomes. | It does not prove that management-company change alone should trigger outreach. |

### Example Capture - Dealer-Backed Active Workflow Block

The Regency outbound campaign response is the first compiled dealer-backed hunter-sales example capture for this page. It is still sanitized and should not be treated as a universal prospecting policy, but it has stronger evidence than the provisional synthetic probes because it comes from the Regency case study, Josh walkthrough context, and the real-example pressure test.

| Capture Field | Read |
| --- | --- |
| Source or signal type | Outbound campaign response from an existing multifamily target, followed by related-property context for Regency and Madison. |
| Evidence label | Real/sanitized dealer example; evidence-backed for the response, site visit, proposal, bid-collection, approval, and closed-won states described in the source artifacts. |
| What the example validates | A prospect reply can convert into opportunity review without becoming automatically quote-ready; related properties need grouped context without merged outcomes; active proposal, bid collection, approved quote, closed-won, and order-readiness states should block duplicate hunter outreach. |
| What it does not validate | It does not validate budget-window target review, prospecting no-response thresholds, manager-change timing, explicit hard-stop scope, soft-negative handling, sensitive-account ownership, or automatic customer-facing outreach. |
| Outcome or holding state | `outbound_response` moved to `site_visit_required`, proposal send, `bid_collection`, approved quote, and closed-won. Any later hunter-sales trigger for the same active workflow should route as `active_owner_context`, not as a new reactivation package. |
| Remaining validation gaps | Capture a separate budget-window, no-response, manager-change, hard-stop, soft-negative, or sensitive-account example before changing those policy defaults. |
| Implications for hunter-sales policy | Preserve `source_origin`, `quote_readiness_distance`, `next_workflow_route`, `RelatedTargetGroupMap`, and `ActiveOwnerContextNote` before deciding whether to pursue, nurture, suppress, or route to an active owner. |

This capture keeps the guardrail narrow:

```text
outbound response
-> opportunity review
-> site visit / discovery / quote-readiness route
-> active proposal or closed-won state
-> block duplicate hunter motion
-> route context to active owner
```

The durable lesson is that hunter-sales systems need to recognize when their job is done. Once a target has become active sales or post-close work, the safe behavior is to preserve context for the active owner instead of starting another prospecting motion.

### Current Policy Corrections

| Correction | Wiki Meaning |
| --- | --- |
| A reply or quote request is not automatically quote-ready. | Opportunity conversion should preserve quote-readiness distance and next route, such as discovery, site visit, quote-readiness review, or quote prep. |
| Source origin changes the first useful package. | Approved outbound reply, direct inbound request, relationship-forwarded request, service-created signal, and formal-feed response should not collapse into one generic reactivation path. |
| Service-created replacement demand is its own route. | It should prepare a replacement opportunity brief, related history, and quote-readiness checklist before any customer-facing action. |
| Shared relationship context does not merge outcomes. | Related properties need grouped context and separate target or opportunity states unless a rep intentionally links them. |
| Active workflow beats new hunter motion. | Proposal, bid collection, approved quote, closed-won, order-readiness, delivery/install, and unresolved service handoff states should route context to the active owner instead of starting hunter outreach. |

### Provisional Status Retained

The provisional probe results did not promote any remaining synthetic probe to `real_example_backed_candidate`, and they did not recommend JSON fixture answer-key changes.

| Provisional Area | Current Decision |
| --- | --- |
| Budget-window target review | Keep provisional; budget timing is leverage for review, not permission to send or queue every target. |
| Prospecting no-response | Keep provisional; touch count, silence age, contact quality, and next trigger are dealer-specific. |
| Manager-change or management-company-change signals | Keep provisional; role level and source reliability probably need splits. |
| Explicit hard stops | Keep provisional until a scoped dealer example clarifies stop type, suppression scope, and override owner. |
| Soft negative responses | Split required; "not now", bounce, wrong person, or vendor selected should not inherit hard suppression by default. |
| Strategic or sensitive accounts | Keep provisional; sensitivity reason, review owner, and allowed preparation must remain policy data. |

The strongest current validation result is the distinction between useful candidate policy and dealer-confirmed policy:

```text
real/sanitized pressure test
-> better guardrail language
-> no fixture promotion without matching dealer judgment
```

### Example Capture - Soft-Negative Split Candidate

The soft-negative response probe is the next compiled hunter-sales example capture for this page. It is not dealer-confirmed. It is a synthetic/sanitized split candidate from the FSCR-012 provisional probe and reasoning-note layer, captured here because it prevents a risky shortcut: treating every negative reply as an explicit hard stop.

| Capture Field | Read |
| --- | --- |
| Source or signal type | Soft-negative response signal in existing multifamily prospecting, such as "not now", wrong person, bounce, vendor already selected, or complaint without an explicit stop. |
| Evidence label | Synthetic/sanitized probe and reasoning note; `split_required`; `policy_parameter_needed`; not `real_example_backed_candidate`. |
| What the example validates | The workflow must classify the response before changing suppression, nurture, contact-correction, deprioritization, or policy-review state. Explicit hard stops and soft negatives are different signals. |
| What it does not validate | It does not validate dealer-approved quiet periods, universal follow-up timing, suppression scope, future trigger rules, or any actual Fit Supply outcome. |
| Outcome or holding state | Hold as `split_required` with no fixture promotion. Keep customer-facing outreach blocked until a rep or policy owner reviews the classified response and allowed next step. |
| Remaining validation gaps | Capture a real or sanitized dealer response with response type, source evidence type, suppression scope, reviewer or override owner, rep judgment, and future trigger. |
| Implications for hunter-sales policy | Add or preserve `ResponseSignal` before `SuppressionRecord`; do not reuse `suppression_no_follow_up` unless the response is an explicit stop, unsubscribe, or policy-confirmed hard stop. |

This capture keeps the policy default narrow:

```text
negative response
-> classify response type
-> choose contact correction, nurture, quiet period, lifecycle watch, policy review, or hard suppression
-> require human review for ambiguous relationship risk or customer-facing next action
```

The durable lesson is that "negative" is not a policy state. A negative response becomes useful only after the system knows whether it is a timing objection, wrong-contact signal, bounce, vendor-cycle signal, relationship-risk complaint, or explicit stop.

## Data Shape Implications

This pattern implies these reusable objects or events:

| Object / Event | Why It Matters |
| --- | --- |
| `DealerProspectingPolicyProfile` | Stores approved or candidate rules for source access, cadence, channels, sender, suppression, approvals, learning, and audit. |
| `SegmentPolicy` | Keeps existing multifamily timing and treatment defaults separate from other segments. |
| `CandidateTargetAccount` | Represents a discovered property before it becomes an active lead or opportunity. |
| `ReactivationWindow` | Encodes timing windows such as multifamily budget-season review. |
| `ReactivationTrigger` | Captures account, property, amenity, service, or source-origin signals. |
| `TargetTreatmentDecision` | Records pursue, nurture, deprioritize, retire, suppress, defer, or convert decisions. |
| `CadenceGuardrail` | Stores spacing, channel limits, quiet windows, stop rules, and policy version. |
| `RepReviewDecision` | Captures accept, edit, reject, defer, suppress, override, or convert decisions. |
| `PolicyEvaluationRun` | Produces traceable input, policy version, guardrail, route, review, and target-state results. |
| `PolicyLearningRecommendation` | Suggests source, play, timing, buyer-path, or cadence changes for human approval. |
| `ResponseSignal` | Classifies negative, soft-negative, hard-stop, bounce, wrong-person, and vendor-selected responses before suppression or nurture changes. |
| `SuppressionRecord` | Preserves stop type, scope, source evidence, override owner, and audit trace for explicit or policy-confirmed stops. |
| `SensitiveAccountReviewPackage` | Routes strategic, house-owned, commercial-risk, complaint-risk, or active-owner-sensitive accounts to the right review owner before outreach. |
| `ReplacementOpportunityBrief` | Carries service-created or installed-base replacement demand into service-to-sales review and quote-readiness work. |
| `QuoteReadinessAccelerationPackage` | Helps direct inbound or high-intent quote requests move faster without pretending they came from outbound reactivation. |
| `RelatedTargetGroupMap` | Keeps shared ownership, management, or relationship context visible while preserving separate target, quote, and outcome states. |

## Wiki And Domain Implications

This page strengthens the `sales` domain and the `agent-workflows` answerability lens. It does not yet justify a new top-level `lead-intelligence` or `prospecting` domain.

The promotion trigger should remain evidence-based: create a first-class domain only after multiple validated pages need shared navigation for lead intelligence, source coverage, prospecting policy, and evaluator-backed workflow contracts.

For now, the sales index should treat hunter sales as an active sub-lane with provisional policy discipline.

## Open Validation Needs

- Capture a real or sanitized budget-window target or review list with amenity confidence, buyer-path confidence, and rep decision.
- Capture a prospecting no-response case with touch count, last touch date, channels, contact confidence, and next meaningful trigger.
- Capture a manager-change or management-company-change signal with role level, source reliability, fitness relevance, and rep judgment.
- Capture an explicit hard-stop example with stop type, suppression scope, source evidence, override owner, and future queue rule.
- Capture a real or sanitized dealer soft-negative response that is not a hard stop, using the split-candidate capture above as the checklist.
- Capture a strategic or sensitive account example where a normal target signal changes the review owner or allowed preparation.
- Keep cadence, channels, sender identity, quiet windows, stop rules, override permissions, and learning thresholds as dealer-policy parameters until validated.
