# Expected Output Structure

The agent must produce output in this structure. Adapt the sections
as needed for the specific workflow under review.

---

```text
# Workflow Pilot Review: [Workflow Name]

## Summary
[One-paragraph description of the workflow and the recommendation]

## Classification
[Candidate for limited pilot | Needs further discovery |
 Needs governance or policy review | Not currently suitable |
 Reject due to excessive risk or autonomy]

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

## Knowledge Accumulation
- **Mechanism exists:** [Yes/No]
- **Knowledge captured:** [What is recorded: source evidence, decisions,
  feedback, failure cases, lessons, approved guidance]
- **Storage or repository:** [Where knowledge is stored]
- **Source traceability:** [Whether source references are preserved]
- **Review owner:** [Who reviews accumulated knowledge]
- **Update or stale-review process:** [How knowledge is kept current]
- **Reuse path:** [How reviewed lessons become reusable guidance]
- **Identified gaps:** [What is missing or not yet captured]

## Human-Review Checkpoints
[List of items requiring human review before proceeding]
```
