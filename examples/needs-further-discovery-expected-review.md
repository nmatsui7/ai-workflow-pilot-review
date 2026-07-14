# Example: Needs Further Discovery

## Input

See `needs-further-discovery-input.md` for the full proposal.

## Expected Reasoning Summary

The agent would:

1. Parse the workflow: AI suggests summaries, categories, urgency,
   routing, and acknowledgements for customer complaints; employees
   review every suggestion. This is a drafting workflow with human
   review at every step.
2. Verify workflow decomposition: 7 steps decomposed; AI assigned to
   summarization, categorization, urgency, routing, and drafting;
   humans review and decide; no autonomous irreversible actions.
3. Check evidence: organization has operational experience with 300
   complaints/week, but no baseline measurements, no prior AI testing,
   and benefits not measured. Evidence is partial.
4. Note positive controls: all suggestions receive human review; no
   automatic sending or case assignment; high-risk categories excluded;
   stop/revise conditions defined; corrections and failure cases may
   be retained.
5. Evaluate failure cases: urgent complaint misclassified (high risk),
   PII exposure through past-case retrieval (high risk), anchoring
   (medium), outdated guidance (medium), generic acknowledgements
   (medium), increased workload (medium).
6. Check knowledge accumulation: detailed plan exists with source
   traceability and monthly review group; but review owner, PII
   removal, deduplication, stale-review, withdrawal, and recognition
   processes are undefined.
7. Verify mandatory gates: accountable owner not named, data-use
   approval pending. Two of six gates not met.
8. Identify adoption risks: workload (300 complaints/week review
   burden), unclear expectations (disagreement resolution undefined),
   role confusion (owner not named), training gap (no plan), lack
   of recognition, evaluation ambiguity (no baselines).
9. Classify as "needs further discovery."

## Expected Output

```
# Workflow Pilot Review: AI-Assisted Customer Complaint Triage

## Summary
A regional utility company proposes using an AI assistant to
summarize customer complaints, suggest categories, recommend urgency,
identify vulnerable customers, route to departments, draft
acknowledgements, and retrieve similar past cases. Employees would
review all AI suggestions before updating the case-management system.
The proposal is well-decomposed, excludes high-risk complaint types,
includes a substantive knowledge-accumulation plan, and defines
stop/revise criteria. However, no accountable owner is named, no
baseline measurements exist, data-use authorization is pending, and
multiple governance decisions remain unresolved.

## Classification
Needs further discovery

## Workflow Analysis
- **Core action:** Summarize, categorize, route, and draft
  acknowledgements for customer complaints
- **Workflow type:** Drafting (AI suggests, humans review and decide)
- **Affected roles:** Customer-service employees (reviewers),
  department representatives (downstream), managers (oversight)
- **Sensitive data involved:** Yes — customer complaints contain PII;
  past resolutions may contain personal information; vulnerable
  customer identification touches sensitive profiles
- **Scope:** One customer-service team, 6 weeks, ~300 complaints/week,
  four complaint categories (billing, service interruptions,
  appointments, service quality)

## Workflow Decomposition
| Step | Action | Support Type |
|------|--------|-------------|
| Receive complaint | Intake from email, web, call centre | Existing system |
| Read complaint | Understand content | Human judgment |
| Summarize | AI generates summary | Generative AI |
| Suggest category | AI recommends category | Generative AI |
| Recommend urgency | AI recommends urgency level | Generative AI |
| Identify vulnerable customers | AI flags potential vulnerability | Generative AI |
| Route to department | AI recommends department | Generative AI |
| Draft acknowledgement | AI drafts response | Generative AI |
| Retrieve similar cases | AI finds past complaints and resolutions | Retrieval |
| Review and decide | Employee accepts, edits, or rejects | Human judgment |
| Update case system | Employee updates record | Existing system |
| Send acknowledgement | Employee sends response | Existing system |

Each step appropriately assigned. AI handles drafting and suggestion;
humans handle judgment and approval. No autonomous irreversible action.

## Positive Controls Identified
- All AI suggestions receive human review before use
- No automatic sending of messages or assignment of cases
- High-risk complaint categories (legal, threats, misconduct,
  medical, emergency) are excluded and escalated through existing
  human processes
- Stop and revision conditions are specifically defined (8 conditions)
- Corrections and failure cases may be retained for knowledge
  accumulation

## Evidence Assessment
- **Completeness:** Yes — workflow decomposed, scope defined, goals
  stated, exclusions identified
- **Factual support:** Partially — operational experience with
  300 complaints/week, but no baseline measurements; no prior AI
  testing; benefits not measured
- **Source quality:** Partially — experienced staff listed as
  knowledge source; some escalation procedures outdated (3 years);
  categories applied inconsistently
- **Privacy:** Partially — PII and vulnerable-customer data
  involved; past resolutions contain personal information; no
  anonymization plan described
- **Failure cases:** Yes — 10 risks identified by the proposal;
  additional failure cases identifiable
- **Human review:** Yes — all AI suggestions require employee review;
  accept/edit/reject mechanism defined
- **Employee impact:** Partially — benefits described but not
  measured; workload impact of reviewing ~300 AI suggestions/week
  not estimated
- **Workload:** Partially — reviewing 300 complaints/week of AI
  suggestions is significant; per-complaint review time not
  estimated; documentation of corrections adds effort
- **Role clarity:** Partially — employees review, departments
  follow up; but accountable owner not named; disagreement resolution
  undefined; accountability for misrouting unclear
- **Output quality:** Partially — AI outputs described; quality
  standards not defined; generic acknowledgements flagged as risk
- **Knowledge accumulation:** Yes — detailed plan for capturing
  corrections, failure cases, and lessons; monthly review group;
  reuse path defined; governance gaps exist but plan is substantive
- **Approval readiness:** Partially — strong workflow design;
  multiple governance decisions unresolved

## Failure Cases
- **Urgent complaint rated as routine:** High — delayed response to
  urgent situation; detected by employee review; mitigated by
  exclusions and review checkpoints; requires escalation triggers
- **Sensitive PII exposed through past-case retrieval:** High —
  privacy violation; detected by employee review; requires
  anonymization of past cases before retrieval
- **Employee anchored to incorrect AI recommendation:** Medium —
  reduces independent judgment; detected by monitoring correction
  patterns; requires consideration of showing AI after initial
  opinion
- **Outdated escalation guidance used by AI:** Medium — incorrect
  routing; detected by employee correction; requires updating
  procedures before pilot
- **Generic acknowledgement does not fit situation:** Medium — poor
  customer experience; detected by employee edit rate; requires
  quality criteria
- **Increased employee workload from reviewing and documenting:**
  Medium — burnout; detected by workload measurement; requires
  per-complaint time estimate
- **Managers treat AI suggestions as final decisions:** Medium —
  undermines employee judgment; detected by employee feedback;
  requires clear communication that AI is advisory
- **Employee improvements used without recognition:** Low-Medium —
  disengagement; detected by employee feedback; requires recognition
  plan
- **Unreviewed lessons promoted to reusable guidance:** Medium —
  incorrect guidance; detected by knowledge review process; requires
  review owner approval
- **Customers mistake AI acknowledgement for final decision:**
  Low-Medium — confusion; detected by customer feedback; requires
  human sends final response

## Adoption Risks
- **Workload increase:** ~300 complaints/week to review; documentation
  of corrections; possible burnout; requires per-complaint time
  estimate
- **Unclear expectations:** Disagreement resolution undefined;
  accountability unclear; requires defined resolution process
- **Staff trust:** AI may be perceived as surveillance; requires
  transparent communication and voluntary participation
- **Role confusion:** Accountable owner not named; requires named
  owner, reviewer, exception handler roles
- **Training gap:** No training plan described; complex multi-step
  workflow; requires training before launch
- **Lack of recognition:** Employee corrections improve process
  without acknowledgment; requires recognition plan
- **Evaluation ambiguity:** No baseline measurements; requires
  baseline completion before launch
- **Weak knowledge sharing:** Plan exists but governance gaps remain;
  requires review owner and approval process
- **Insufficient experienced staff input:** Staff listed as knowledge
  source but role in design unclear; requires involvement in
  workflow design
- **Efficiency gains become additional workload:** "Reduce time on
  routine classification" may increase review burden; requires
  total-effort measurement
- **Unclear ownership of improvements:** Post-pilot knowledge owner
  unclear; requires assignment before pilot
- **Premature reuse of unreviewed knowledge:** Monthly review group
  defined but approval process not; requires knowledge-maturity
  stages

## Knowledge Accumulation
- **Mechanism exists:** Yes — detailed plan for capturing AI
  recommendations, employee corrections, failure cases, and lessons
- **Knowledge captured:** Source evidence, decisions, reviewer
  feedback, failure cases, references to source complaints
- **Storage or repository:** Case-management system; monthly review
  group
- **Source traceability:** Yes — references to source complaints
- **Review owner:** Not assigned — monthly review group exists but
  no named approval authority
- **Update or stale-review process:** Monthly review group defined;
  stale-date and withdrawal process not defined
- **Reuse path:** Reviewed lessons → category definitions, escalation
  examples, acknowledgement templates, training material, AI skill
  reference files
- **Identified gaps:** No approval authority for lessons; no PII
  removal process; no duplicate/conflict resolution; no stale-date
  process; no incorrect-guidance withdrawal process; no employee
  recognition for contributions

## Risks and Gaps
- Accountable workflow owner not named (mandatory gate)
- Data-use authorization for past complaint records not obtained
  (mandatory gate)
- No baseline measurements for processing time, routing accuracy,
  or urgency accuracy
- Disagreement resolution process undefined
- Review-time limits undefined
- Anchoring mitigation not addressed
- Accountability for incorrect prioritization unclear
- Knowledge review ownership and approval process undefined
- PII anonymization for past-case retrieval not planned
- Employee recognition for contributions not addressed
- Training plan not described

## Questions for Domain Owner
1. Who is the accountable workflow owner?
2. What are the baseline measurements for processing time, routing
   accuracy, and urgency accuracy?
3. How will past complaint data be anonymized or protected?
4. Who resolves disagreements between employees and AI?
5. How much review time per complaint is acceptable?
6. Should AI suggestions be shown before or after the employee forms
   an initial opinion?
7. Who is accountable for an incorrectly prioritized complaint?
8. Which errors require immediate escalation?
9. How will conflicting guidance be handled?
10. Who approves lessons for reuse?
11. How will PII be removed from lessons before reuse?
12. What recognition plan exists for employees who identify reusable
    improvements?

## Recommendation
The proposal demonstrates strong workflow understanding, thorough
decomposition, appropriate tool selection, thoughtful exclusions,
and a substantive knowledge-accumulation plan. It is one of the more
complete proposals evaluated.

However, two mandatory gates are not met (accountable owner,
data-use approval), and several governance decisions remain
unresolved (disagreement resolution, review time limits, anchoring
mitigation, accountability for errors).

**Classify as "needs further discovery."**

Before reclassifying as a candidate for limited pilot, complete:

1. Name the accountable workflow owner
2. Complete baseline measurements
3. Obtain data-use authorization for past complaint records
4. Define PII anonymization process
5. Resolve the 12 questions above (at minimum, questions 1-8)

Once those are complete, the proposal is well-positioned for a
limited pilot.

## Human-Review Checkpoints
1. Confirm the accountable workflow owner is named and empowered
2. Confirm baseline measurements are completed and documented
3. Confirm data-use authorization for past complaint records
4. Confirm PII anonymization process for past-case retrieval
5. Confirm disagreement-resolution process
6. Confirm acceptable review-time threshold per complaint
7. Confirm anchoring-mitigation approach
8. Confirm accountability for incorrectly prioritized complaints
9. Confirm training plan for customer-service employees
10. Confirm recognition plan for employee contributions
11. Confirm knowledge-review ownership and approval process
12. Confirm that all success metrics have measurable baselines
```

## Human-Review Notes

A human reviewer should:

- Recognize that this is a strong proposal with clear workflow
  understanding and thoughtful controls.
- Note that the two unmet mandatory gates (owner, data-use) are
  addressable — this is not a fundamental design flaw.
- Consider whether the knowledge-accumulation gaps (approval, PII
  removal, stale-review) should block the pilot or be resolved
  during it.
- Decide whether the anchoring risk (showing AI before vs. after
  initial opinion) should be tested during the pilot or resolved
  beforehand.
- Confirm that the 300 complaints/week review burden is realistic
  for one team and does not create hidden workload.
- Note that the proposal's own risk identification is thorough —
  this suggests organizational awareness that supports responsible
  pilot design.
