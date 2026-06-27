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
provenance_notes: Synthesized from roadmap FSCR-012 as a design-hypothesis sales pattern. The source family includes candidate policy defaults and synthetic fixture labels, so this page must not be treated as approved dealer policy or current Fit Supply operations.
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

## Wiki And Domain Implications

This page strengthens the `sales` domain and the `agent-workflows` answerability lens. It does not yet justify a new top-level `lead-intelligence` or `prospecting` domain.

The promotion trigger should remain evidence-based: create a first-class domain only after multiple validated pages need shared navigation for lead intelligence, source coverage, prospecting policy, and evaluator-backed workflow contracts.

For now, the sales index should treat hunter sales as an active sub-lane with provisional policy discipline.

## Open Validation Needs

- Confirm exact existing multifamily budget-review timing and prep lead time.
- Validate which source signals are reliable enough to trigger rep review.
- Validate buyer-path patterns for existing multifamily and compare them with new construction, schools, hospitality, and public-sector paths.
- Tune no-response thresholds, long-tail nurture intervals, and competitor-cycle treatment.
- Decide which soft negative responses should split from hard do-not-contact suppression.
- Confirm sensitive-account review ownership and escalation path.
- Validate cadence, channels, sender identity, quiet windows, stop rules, and override permissions.
- Decide which outcome evidence is strong enough to recommend future policy changes.
