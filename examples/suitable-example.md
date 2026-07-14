# Example: Suitable for Pilot

## Input

**Workflow description:**
We want to pilot an AI tool that helps our customer support team
summarize incoming support tickets. The AI would read each ticket
and generate a 2-3 sentence summary showing the issue category,
urgency, and key details. Agents would review the summary before
adding it to the ticket record. The AI would not respond to
customers directly.

**Proposed scope:**
8 customer support agents on the Tier 1 team, 6-week pilot period,
using the existing ticketing system (Zendesk). The AI summary would
appear as a draft in an internal field only.

**Stated goal:**
Reduce the time agents spend writing ticket summaries by 30%, so they
can spend more time on complex customer issues.

**Evidence:**
We ran a manual test with 50 tickets from last month. An agent wrote
summaries manually, then the AI generated summaries for the same
tickets. The AI summaries were rated as "equally useful" or "more
useful" by 42 of 50 tickets by a senior agent. Average time per
summary was 45 seconds manually vs. 8 seconds with AI assistance.

## Expected Reasoning Summary

The agent would:

1. Parse the workflow: AI generates draft summaries of support
   tickets; humans review before saving.
2. Classify as drafting workflow; no autonomous decisions.
3. Note that sensitive customer data is involved but stays within
   existing ticketing system.
4. Check evidence: manual test with 50 tickets, comparison data,
   time savings measured, quality rated by senior agent. Evidence
   is relevant and from a credible source.
5. Evaluate failure cases: hallucinated summaries (low risk because
   agents review), privacy (contained within Zendesk), role clarity
   (agents are reviewers), training (minimal since summaries are
   simple).
6. Identify scope is within pilot limits (8 agents, 6 weeks, one
   team).
7. Note that the AI does not contact customers directly.
8. Classify as "suitable for pilot" with conditions.

## Expected Output

```
# Workflow Pilot Review: AI Ticket Summary for Support Team

## Summary
AI-generated draft summaries of incoming support tickets for Tier 1
agents to review and approve before saving. The workflow is well-scoped,
has supporting evidence, and includes human review at every step.

## Classification
Suitable for pilot

## Workflow Analysis
- **Core action:** Generate draft summaries of support tickets
- **Workflow type:** Drafting
- **Affected roles:** Tier 1 customer support agents
- **Sensitive data involved:** Yes - customer support ticket content
- **Scope:** 8 agents, 6 weeks, Zendesk ticketing system

## Evidence Assessment
- **Completeness:** Met - description, scope, and goal are clear
- **Factual support:** Met - manual test with 50 tickets, quality
  ratings, time measurements
- **Source quality:** Met - evidence from internal test, rated by
  senior agent
- **Privacy:** Partially met - customer data in Zendesk, no external
  data flow described
- **Failure cases:** Met - hallucination risk mitigated by human review
- **Human review:** Met - agents review every summary before saving
- **Employee impact:** Positive - reduces repetitive work
- **Workload:** Met - minimal training needed, 8-second summaries
- **Role clarity:** Met - agents review, senior agent validates
- **Accessibility:** Met - within existing system
- **Output quality:** Met - quality rated in evidence
- **Approval readiness:** Met - all critical criteria satisfied

## Failure Cases
- **Hallucinated summary:** Low impact, detected by agent review
- **Privacy exposure:** Low impact, data stays in Zendesk
- **Training gap:** Low impact, simple workflow

## Risks and Gaps
- Privacy assessment partially met: no explicit data handling policy
  described for AI model access to Zendesk data

## Questions for Domain Owner
1. Does the AI tool access Zendesk via API, and is that API approved?
2. Is customer data sent to an external AI provider, or is the model
   hosted locally?
3. What happens if the AI summary is inaccurate - does the agent
   delete it or edit it?

## Recommendation
Proceed with pilot. Address the Zendesk API and data flow questions
before launching. Include a feedback mechanism for agents to rate
AI summary quality during the pilot.

## Human-Review Checkpoints
1. Confirm Zendesk API access is approved
2. Confirm data handling policy for AI model
3. Confirm pilot success metrics (30% time reduction)
4. Confirm agent participation is voluntary
```

## Human-Review Notes

A human reviewer should:

- Confirm the Zendesk integration is technically approved and does not
  violate data agreements.
- Confirm that customer data is not sent to an external AI provider
  without appropriate safeguards.
- Define what "equally useful" means in the evidence test and whether
  the quality bar is sufficient for production use.
- Decide whether 30% time reduction is the right primary metric or
  whether agent satisfaction should also be measured.
