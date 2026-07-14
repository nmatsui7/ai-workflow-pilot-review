---
name: ai-workflow-pilot-review
description: >
  Activate when a user proposes an AI-assisted workplace workflow and asks
  whether it is suitable for a limited pilot. This includes requests to evaluate
  feasibility, risks, readiness, or to produce a pilot recommendation for any
  proposed AI-assisted process that would affect employees, customers, or
  internal operations.
---

# AI-Assisted Workplace Workflow Pilot Review

## 1. Business Purpose

This skill evaluates proposed AI-assisted workplace workflows to determine
whether they are suitable for a limited pilot deployment. It produces a
structured review covering evidence quality, risks, privacy, workload,
role clarity, training needs, and evaluation criteria.

The skill does not approve or execute pilots. It produces reviewable
drafts that require explicit human decision-making.

## 2. Required Inputs

The agent must receive the following before proceeding:

- **Workflow description:** What the AI would do, in plain language.
- **Proposed scope:** Who is affected, how many people, what systems.
- **Stated goal:** What problem the workflow solves or what it improves.
- **Evidence or rationale:** Why the requester believes this is worthwhile.

If any required input is missing, the agent must ask for it before
continuing. See Section 10 for missing-information handling.

## 3. Workflow Steps

Follow these steps in order. Do not skip steps.

### Step 1: Parse and Classify

- Extract the workflow's core action (what the AI does).
- Identify affected roles (employees, customers, both).
- Classify the workflow type: information retrieval, drafting,
  recommendation, approval, or execution.
- Note whether the workflow touches sensitive data.

### Step 1a: Workflow Analysis

Before evaluating criteria, verify that the proposal addresses
fundamental workflow questions:

- Does the proposal begin with a concrete workflow problem (repeated,
  time-consuming, or frustrating work), not with a tool preference?
- Has the workflow been decomposed into individual steps?
- Has each step been assigned to the appropriate type of support:
  generative AI, search/retrieval, templates, deterministic
  automation, or human judgment?
- Are steps that require human judgment clearly identified?
- Can the workflow be tested as a small and reversible improvement?
- Can people familiar with the work review the proposed workflow?

If the proposal selects AI before understanding the workflow, flag
this as a significant gap. Not every workflow step requires generative
AI — templates, search, or deterministic automation may be more
appropriate.

When assessing workflow design, organizational learning, employee
impact, or the maturity of reusable knowledge, consult
`references/method-notes.md`.

### Step 2: Gather Context

- Ask clarifying questions if the description is ambiguous.
- Request specific examples of inputs and outputs.
- Request any existing evidence (pilot data, benchmarks, prior attempts).
- Record what is known versus what is assumed.

### Step 3: Evaluate Against Criteria

Apply the review checklist in `references/review-checklist.md` and the
pilot selection criteria in `references/pilot-selection-criteria.md`.
For each criterion, assign one of the following statuses:

- **Met:** Evidence supports this criterion.
- **Partially met:** Some evidence exists but gaps remain.
- **Not met:** No evidence or clear deficiency.
- **Not applicable:** Criterion does not apply to this workflow.

### Step 4: Identify Failure Cases

Compare the workflow against known failure patterns in
`references/failure-cases.md` and adoption risk types in
`references/adoption-risk-types.md`. For each applicable failure case
or risk type:

- Describe how it could occur in this specific workflow.
- Estimate the impact (low, medium, high).
- Identify whether detection is possible.
- Note whether human escalation is required.

### Step 5: Check Knowledge Sources

Verify that the workflow relies on approved knowledge sources only.
See Section 4 for the approved list. Flag any unapproved sources.

If the proposal references lessons, findings, or observations from
prior work, check whether they have been reviewed using the maturity
stages in `references/knowledge-review-guidance.md`. Unreviewed
observations must not be treated as validated knowledge.

### Step 6: Apply Business Rules

Apply all rules in `references/workflow-rules.md`. For any rule that
cannot be satisfied, document why and recommend a mitigation.

### Step 7: Classify and Recommend

Classify the workflow into one of three outcomes:

- **Suitable for pilot:** All critical criteria are met or have
  acceptable mitigations. Risks are manageable. Proceed with
  conditions.
- **Unsuitable for pilot:** Critical criteria are not met, risks
  are too high, or the proposal is fundamentally flawed. Do not
  recommend a pilot.
- **Incomplete:** The proposal lacks sufficient information to
  evaluate. Request missing details before classifying.

**Mandatory gates for "Suitable for pilot" classification:**

All six of the following must be confirmed before a workflow can be
classified as suitable for a limited pilot. If any gate is not met,
classify as unsuitable or incomplete.

1. **Accountable workflow owner is identified.** A specific person
   is responsible for the workflow during and after the pilot.
2. **Qualified human reviewer is available.** A person with relevant
   expertise will review AI output before it is used.
3. **Some supporting workflow evidence exists.** At least one piece
   of evidence describes how the work currently happens or how the
   proposed workflow was tested.
4. **Required data use is approved.** The data the AI workflow needs
   is available and its use has been authorized.
5. **Stop or revise criteria are defined.** The pilot includes
   explicit conditions under which it will be stopped or revised.
6. **The workflow does not autonomously perform irreversible or
   high-impact actions.** All consequential actions require human
   approval.

If the proposal references prior lessons or findings, note their
knowledge maturity stage (see `references/knowledge-review-guidance.md`).
Unreviewed observations should not be the sole basis for a suitability
recommendation.

### Step 8: Generate Output

Produce the structured output described in Section 7.

### Step 9: Human Review

Present the output for human review. Do not proceed beyond this point
without explicit human approval. See Section 8 for human-review
checkpoints.

## 4. Approved Knowledge Sources

The agent may use these sources to inform its evaluation:

- The workflow description provided by the user
- The reference files in this skill folder
- General knowledge about AI capabilities and limitations
- Stated organizational constraints provided by the user

The agent must not use or reference:

- External databases or APIs not provided by the user
- Real employee or customer data
- Third-party tools or services
- Assumed organizational policies not explicitly stated

If the user references a policy or document the agent cannot access,
flag it as an unresolved assumption.

## 5. Business Rules

1. **No execution.** The agent does not create, deploy, configure, or
   activate any workflow. It only produces reviews and recommendations.
2. **No real data.** The agent must not request, access, or use real
   employee data, customer data, or credentials.
3. **Conservative defaults.** When information is missing, default to
   "not met" or "incomplete" rather than assuming compliance.
4. **Explicit uncertainty.** State assumptions clearly. Label them as
   "assumption" in the output.
5. **Human approval required.** No recommendation is final until a
   human reviewer approves it.
6. **Escalate, do not hide.** If a critical risk is found, escalate
   it. Do not downplay or omit it.
7. **Scope limits.** A limited pilot is defined by its characteristics,
   not by participant counts or duration. A limited pilot has:
   - Bounded workflow and user group
   - Limited consequences
   - Reversible outcomes
   - Named owner and reviewer
   - Measurable baseline
   - Manageable reviewer workload
   - Sufficient duration to collect evidence
   - Explicit stop, revise, and escalation criteria

   Participant counts and duration are domain-owner decisions, not
   defaults. Record them as part of the proposal.
8. **Privacy first.** If the workflow touches personal data, PII,
   financial data, health data, or authentication credentials, flag
   it immediately as a high-risk element.

## 6. Expected Output Structure

The agent must produce output in this structure:

```
# Workflow Pilot Review: [Workflow Name]

## Summary
[One-paragraph description of the workflow and the recommendation]

## Classification
[Suitable for pilot | Unsuitable for pilot | Incomplete]

## Workflow Analysis
- **Core action:** [What the AI does]
- **Workflow type:** [Information retrieval | Drafting | Recommendation | Approval | Execution]
- **Affected roles:** [List of roles]
- **Sensitive data involved:** [Yes/No + type if yes]
- **Scope:** [Number of participants, duration, systems]

## Evidence Assessment
[For each criterion from the review checklist:]
- **Criterion:** [Status] - [Evidence summary or gap]

## Failure Cases
[For each applicable failure case:]
- **Scenario:** [Description]
- **Impact:** [Low | Medium | High]
- **Detection:** [How it could be detected]
- **Mitigation:** [Recommended action]

## Risks and Gaps
[Summary of identified risks, gaps, and unresolved questions]

## Questions for Domain Owner
[Specific questions that need answers before a decision can be made]

## Recommendation
[Detailed recommendation with conditions, if any]

## Human-Review Checkpoints
[List of items requiring human review before proceeding]
```

## 7. Human-Review Checkpoints

The following items require explicit human review before the
recommendation is considered complete:

1. **Privacy assessment:** A human must confirm whether the data
   classification is correct and whether privacy controls are adequate.
2. **Risk acceptability:** A human must confirm that identified risks
   are acceptable for the organization.
3. **Resource availability:** A human must confirm that training,
   staffing, and time resources are available.
4. **Approval authority:** A human with appropriate authority must
   approve the pilot recommendation.
5. **Success criteria:** A human must confirm that the proposed
   evaluation metrics are appropriate.

The agent must flag these checkpoints in its output and must not
proceed as if they have been completed.

## 8. Actions the Agent Must Not Perform

- Deploy, configure, or activate any AI workflow
- Send real emails, messages, or notifications
- Access real employee or customer data
- Make hiring, firing, or HR decisions
- Approve budgets or allocate resources
- Modify organizational policies
- Access external systems or APIs
- Assume organizational approval or endorsement
- Present draft recommendations as final decisions

## 9. Missing-Information Handling

When required information is missing:

1. Stop and identify exactly what is missing.
2. State what the missing information prevents the agent from evaluating.
3. Provide a specific question or request for the missing information.
4. If the missing information is critical, classify the workflow as
   "Incomplete" and do not produce a recommendation.
5. If the missing information is non-critical, note the gap and proceed
   with a conditional recommendation, clearly labeled.

Never guess or assume critical information. Default to "Incomplete"
when in doubt.

## 10. Escalation Conditions

Escalate immediately when:

- The workflow involves sensitive data without clear privacy controls
- The proposed scope does not meet the limited pilot characteristics
  (see Section 5, rule 7)
- The workflow involves autonomous decision-making with no human override
- The agent detects a conflict of interest or ethical concern
- The evidence contradicts the stated goal
- The proposal requires capabilities the agent cannot verify
- The user requests the agent to execute rather than review

When escalating, state:
- What triggered the escalation
- What information is needed
- Who should review it (if known)

## 11. Final Validation Checks

Before presenting the output, verify:

- [ ] All required inputs were received or flagged as missing
- [ ] Each review criterion has a status (Met, Partially met, Not met, N/A)
- [ ] At least one failure case was evaluated
- [ ] Privacy implications are addressed
- [ ] All assumptions are labeled
- [ ] Human-review checkpoints are listed
- [ ] The classification matches the evidence (no contradictory recommendation)
- [ ] The output does not contain private chain-of-thought
- [ ] The recommendation includes conditions or is clearly justified
