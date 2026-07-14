# Example: Needs Further Discovery

## Input

**Workflow description:**
We want to use AI to help with employee onboarding. The AI would
answer new hire questions about company policies and processes.

**Proposed scope:**
All new hires across the company.

**Stated goal:**
Make onboarding faster and reduce the HR team's workload.

**Evidence:**
We think AI would be good at this because it can answer questions
quickly.

## Expected Reasoning Summary

The agent would:

1. Parse the workflow: AI answers new hire questions about policies.
2. Note the description is very vague - what policies? what format?
   what channel?
3. Check scope: "all new hires across the company" is too broad for
   a limited pilot.
4. Check evidence: "we think AI would be good at this" is not
   evidence; no testing, no benchmarks, no prior attempts.
5. Identify multiple missing inputs: no specific workflow steps, no
   data sources described, no fallback plan, no training plan, no
   role assignments.
6. Classify as "needs further discovery" and request missing information.

## Expected Output

```
# Workflow Pilot Review: AI Onboarding Assistant

## Summary
A proposal to use AI to answer new hire questions about company
policies and processes. The proposal lacks sufficient detail to
evaluate. Critical information is missing about data sources,
workflow design, scope, and evidence.

## Classification
Needs further discovery

## Workflow Analysis
- **Core action:** Answer new hire questions about policies
- **Workflow type:** Information retrieval (likely, but unclear)
- **Affected roles:** New hires, HR team
- **Sensitive data involved:** Unknown - depends on what policies
  are included
- **Scope:** "All new hires across the company" - exceeds small
  pilot limits

## Evidence Assessment
- **Completeness:** No — description is too vague to evaluate
- **Factual support:** No — no evidence provided; statement
  of belief ("we think AI would be good at this") is not evidence
- **Source quality:** N/A — no sources cited
- **Privacy:** Unknown — cannot assess without knowing what data
  the AI would access
- **Failure cases:** No — no failure cases identified
- **Human review:** Unknown — no review process described
- **Employee impact:** Unknown — impact on new hires and HR not
  assessed
- **Workload:** Unknown — training needs not assessed
- **Role clarity:** No — no roles assigned
- **Accessibility:** Unknown — not addressed
- **Output quality:** Unknown — no quality standards defined
- **Approval readiness:** No — proposal is too incomplete

## Failure Cases
Cannot evaluate failure cases without more information about the
workflow design.

## Risks and Gaps
- No specific policies or knowledge sources identified
- No data source for AI answers described
- No workflow steps beyond "answer questions"
- Scope exceeds limited pilot characteristics
- No evidence provided
- No roles assigned
- No training plan
- No fallback for AI errors

## Questions for Domain Owner
1. What specific company policies would the AI answer questions
   about? (HR, IT, benefits, compliance, etc.)
2. Where would the AI get its answers? (policy documents, knowledge
   base, HR team input?)
3. What channel would new hires use to ask questions? (chat, email,
   web portal?)
4. Would HR review AI answers before they are shown to new hires,
   or would the AI respond directly?
5. Can the scope be limited to one department or location for a
   pilot?
6. Is there any existing onboarding feedback that suggests this
   would be valuable?
7. What happens if the AI gives incorrect policy information?

## Recommendation
Cannot classify this proposal without additional information. The
proposal needs:

1. A specific workflow description with step-by-step process
2. Identification of knowledge sources (what policies, in what
   format)
3. Evidence of value (survey data, time studies, prior attempts)
4. Scope reduction to a single department or location
5. Role assignments for oversight and exception handling

Please provide the missing information and resubmit for review.

## Human-Review Checkpoints
1. Confirm what policies should be included
2. Confirm knowledge source availability
3. Confirm scope reduction is acceptable
4. Confirm evidence requirements
```

## Human-Review Notes

A human reviewer should:

- Recognize that this proposal is a common starting point but
  needs significant development before evaluation.
- Consider whether the HR team has bandwidth to provide the missing
  information or whether this proposal should be deprioritized.
- Decide whether to ask for all missing information at once or
  iteratively.
- Note that "all new hires across the company" suggests the scope
  needs to be reduced for a pilot.
- Consider whether the underlying need (faster onboarding, less
  HR workload) could be addressed with a simpler solution.
