# Review Checklist

Use this checklist for every workflow evaluation. For each item, assign
one of these statuses:

- **Yes:** Evidence supports this criterion.
- **No:** No evidence or clear deficiency.
- **Unknown:** Insufficient information to assess.
- **N/A:** Criterion does not apply to this workflow.

For nuanced findings, add a brief evidence or notes field rather
than inventing additional status labels.

## Completeness

- [ ] Workflow description is specific enough to evaluate
- [ ] Input data and output format are clearly described
- [ ] Affected roles are identified
- [ ] Scope is defined (participants, duration, systems)
- [ ] Success criteria or measurable goals are stated

## Factual Support

- [ ] At least one piece of evidence supports the workflow
- [ ] Evidence is from a credible or verifiable source
- [ ] Prior attempts or related work are disclosed (if any)
- [ ] Assumptions are labeled and not presented as facts

## Source Quality

- [ ] Evidence sources are identified and accessible
- [ ] Sources are recent enough to be relevant
- [ ] Sources are independent of the proposal (not self-referencing)
- [ ] No circular reasoning (evidence does not rely on the outcome)

## Privacy and Confidentiality

- [ ] Data types involved are classified
- [ ] Personal data, PII, financial data, or health data is flagged
- [ ] Data handling and storage are described
- [ ] Consent or legal basis is addressed (if applicable)
- [ ] Data retention and deletion are addressed (if applicable)

## Foreseeable Failure Cases

- [ ] At least three failure cases are identified
- [ ] Each failure case has an estimated impact level
- [ ] Each failure case has a detection method
- [ ] Each failure case has a mitigation plan
- [ ] Cascading failures are considered

## Human-Review Requirements

- [ ] Human override exists for all AI decisions
- [ ] Review checkpoints are defined in the workflow
- [ ] Escalation paths are identified
- [ ] Clear distinction between AI draft and human approval

## Employee and Customer Impact

- [ ] Impact on affected employees is described
- [ ] Impact on affected customers is described
- [ ] Positive and negative impacts are both considered
- [ ] Impact on employee autonomy is addressed
- [ ] Impact on customer trust is addressed

## Workload Implications

- [ ] Training time requirements are estimated
- [ ] Transition period workload is considered
- [ ] Ongoing maintenance burden is estimated
- [ ] Resource requirements are realistic for the organization

## Role Clarity

- [ ] Who is responsible for oversight is defined
- [ ] Who approves changes is defined
- [ ] Who handles exceptions is defined
- [ ] Who monitors the pilot is defined
- [ ] Accountability is assigned, not ambiguous

## Accessibility

- [ ] The workflow is accessible to all affected users
- [ ] Accessibility requirements (disability, language) are addressed
- [ ] Training materials are available and appropriate
- [ ] Support channels are defined

## Output Quality

- [ ] The AI output format is clearly described
- [ ] Quality standards for AI output are defined
- [ ] Error handling for bad output is described
- [ ] Fallback procedures exist when AI output is unacceptable

## Approval Readiness

- [ ] All critical criteria are met or have mitigations
- [ ] Risks are within acceptable thresholds
- [ ] Resources are available
- [ ] Stakeholders are identified and aligned
- [ ] The proposal meets the limited pilot characteristics (bounded
  workflow and user group, limited consequences, reversible outcomes,
  named owner and reviewer, measurable baseline, manageable reviewer
  workload, sufficient duration, explicit stop/revise criteria)

## Workflow Governance Checks

These checks are advisory by default. They help identify gaps and
improvement opportunities. Answer each item with: Yes, No, Unknown,
or Not applicable.

| # | Check | Answer |
|---|-------|--------|
| 1 | Is the proposal based on evidence of how the work currently happens? | |
| 2 | Has the workflow been broken into individual steps? | |
| 3 | Has each step been assigned to the appropriate type of support (generative AI, search, templates, automation, human judgment)? | |
| 4 | Have experienced staff reviewed the proposed workflow? | |
| 5 | Are important exceptions and failure cases documented? | |
| 6 | Has the expected reviewer workload been estimated? | |
| 7 | Could the proposal increase workload despite claimed efficiency? | |
| 8 | Is there a plan to recognize employee contributions to workflow improvement? | |
| 9 | Are reusable lessons separated from informal or unvalidated observations? | |
| 10 | Is there a date or trigger for reviewing accumulated knowledge? | |
| 11 | Are AI outputs still treated as drafts or recommendations? | |

## Knowledge Accumulation

Each item must be answered with: Yes, No, Unknown, or Not applicable.

- [ ] Does the project capture source evidence?
- [ ] Does it record reviewer feedback and decisions?
- [ ] Are failure cases and exceptions retained?
- [ ] Is there a defined owner for reviewing accumulated knowledge?
- [ ] Can stale, incorrect, or conflicting knowledge be revised or
  retired?
- [ ] Is there a path for promoting reviewed lessons into examples,
  playbooks, reference files, or skills?

## Mandatory Gates for Pilot Classification

The following six gates must all be confirmed before a workflow can
be classified as "Candidate for limited pilot." If any gate is not
met, the workflow cannot receive that classification.

| # | Gate | Confirmed |
|---|------|-----------|
| 1 | Accountable workflow owner is identified | |
| 2 | Qualified human reviewer is available | |
| 3 | Some supporting workflow evidence exists | |
| 4 | Required data use is approved | |
| 5 | Stop or revise criteria are defined | |
| 6 | Workflow does not autonomously perform irreversible or high-impact actions | |
