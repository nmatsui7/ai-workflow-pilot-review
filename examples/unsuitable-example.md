# Example: Unsuitable for Pilot

## Input

**Workflow description:**
We want to use AI to automatically respond to customer complaints on
social media. The AI would read incoming posts, classify them by
sentiment and topic, draft a response, and post it publicly without
human review. The goal is to reduce response time from 4 hours to
under 5 minutes.

**Proposed scope:**
All customer-facing social media accounts (Twitter, Facebook,
Instagram), all customer complaints, company-wide rollout after a
2-week "pilot."

**Stated goal:**
Dramatically improve customer response times and reduce the social
media team's workload by 70%.

**Evidence:**
We saw a demo from a vendor that showed AI responding to sample
tweets. The responses looked professional and helpful. The vendor
claims 90% accuracy on sentiment classification.

## Expected Reasoning Summary

The agent would:

1. Parse the workflow: AI autonomously classifies and responds to
   public customer complaints on social media.
2. Classify as execution workflow with autonomous public actions.
3. Note sensitive data: customer complaints may contain PII, financial
   data, or health information.
4. Check evidence: vendor demo is not independent evidence; 90%
   accuracy claim is unverified; no internal testing described.
5. Evaluate failure cases: hallucinated responses posted publicly
   (high impact), privacy breach (high impact), no human override
   (critical), scope exceeds pilot limits.
6. Note multiple critical issues: no human review, public-facing
   actions, unverified evidence, scope too large.
7. Classify as "unsuitable for pilot."

## Expected Output

```
# Workflow Pilot Review: AI Auto-Response to Social Media Complaints

## Summary
An AI system would autonomously classify and publicly respond to
customer complaints on social media without human review. This
workflow has critical risks including public-facing autonomous
actions, unverified evidence, excessive scope, and no human override.

## Classification
Unsuitable for pilot

## Workflow Analysis
- **Core action:** Classify complaints and post public responses
  autonomously
- **Workflow type:** Execution
- **Affected roles:** Social media team, customers, public audience
- **Sensitive data involved:** Yes - customer complaints may contain
  PII, financial or health information
- **Scope:** All social media accounts, all complaints, company-wide

## Evidence Assessment
- **Completeness:** Partially met - scope and goal stated, but
  success criteria are vague
- **Factual support:** Not met - vendor demo is not independent
  evidence; no internal testing
- **Source quality:** Not met - vendor claims are not verified;
  demo was with sample data, not real complaints
- **Privacy:** Not met - public posting of AI responses to
  potentially sensitive complaints; no privacy controls described
- **Failure cases:** Not met - no failure cases identified by
  proposer; autonomous public actions have no override
- **Human review:** Not met - workflow explicitly excludes human
  review
- **Employee impact:** Negative - removes human judgment from
  sensitive customer interactions
- **Workload:** Not met - no training plan; transition from manual
  to autonomous is extreme
- **Role clarity:** Not met - who handles escalated complaints?
  who monitors AI accuracy?
- **Accessibility:** Not met - no accessibility considerations
  for AI-generated public responses
- **Output quality:** Not met - no quality standards for
  public-facing AI text
- **Approval readiness:** Not met - multiple critical criteria
  failures

## Failure Cases
- **Hallucinated public response:** High impact - incorrect or
  offensive response posted publicly; reputation damage; no
  detection mechanism described
- **Privacy breach:** High impact - customer PII included in
  public AI response; regulatory exposure
- **Excessive autonomy:** Critical - no human override for
  public-facing actions
- **Evidence gap:** High impact - vendor demo does not prove
  real-world performance
- **Scope creep:** High impact - company-wide scope is not
  a pilot

## Risks and Gaps
- No human review for public-facing actions
- No independent evidence of effectiveness
- Scope far exceeds small pilot limits
- No privacy controls for customer data
- No fallback procedure for AI failure
- No training plan
- No role assignments for oversight

## Questions for Domain Owner
1. Is there a requirement for human review before any public-facing
   AI response?
2. Has the vendor's accuracy claim been independently verified?
3. Is there a legal review of AI-generated public responses to
   customer complaints?
4. What is the plan if the AI posts an incorrect or harmful response?

## Recommendation
Do not proceed with this workflow as described. The fundamental
design (autonomous public responses without human review) is not
suitable for a pilot. If the goal is to assist the social media
team, consider a drafting workflow where AI generates draft
responses that humans review before posting. This would address
the autonomy, privacy, and quality concerns while still reducing
response time.

## Human-Review Checkpoints
1. The entire proposal requires redesign before re-evaluation
2. Human review requirement must be added for public-facing actions
3. Evidence must be independently verified
4. Scope must be reduced to a single account and limited duration
```

## Human-Review Notes

A human reviewer should:

- Recognize that the core issue is the absence of human review for
  public actions, not the specific technology.
- Consider whether the vendor demo is sufficient evidence or whether
  a controlled internal test is needed.
- Evaluate whether the 70% workload reduction claim is realistic
  and whether it accounts for the time needed to handle AI errors.
- Decide whether this proposal should be reworked into a drafting
  workflow or rejected entirely.
