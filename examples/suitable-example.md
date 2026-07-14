# Example: Suitable for Pilot

## Input

**Workflow description:**
Our customer support team manually summarizes incoming tickets before
handing them off to specialist teams. Each agent spends about 45
seconds per ticket writing a 2-3 sentence summary. We want to pilot
an AI tool that drafts these summaries automatically. Agents would
review each draft, edit if needed, and save it to the ticket record.
The AI would not contact customers directly.

**Proposed scope:**
8 Tier 1 support agents, 6-week pilot, using our existing Zendesk
instance. The AI summary appears as a draft in an internal field only.

**Stated goal:**
Reduce time spent on ticket summaries by 30%, from 45 seconds to
about 30 seconds per ticket on average.

**Evidence:**
Two senior agents independently tested the AI tool with 50 tickets
from last month. They rated each AI summary as "usable as-is,"
"usable with minor edits," or "not usable." Results: 34 usable
as-is, 10 usable with edits, 6 not usable. Time per summary: 42
seconds manually vs. 12 seconds with AI assistance (including review).
Baseline: agents currently summarize approximately 120 tickets per
day across the team.

**Experienced staff involvement:**
The two senior agents who tested the tool have 4+ years of support
experience. They identified three edge cases where the AI summary
missed urgency markers, and these were added to the quality criteria.

**Lesson recording plan:**
During the pilot, agents will log AI summary quality ratings in a
shared spreadsheet. A weekly 15-minute review meeting will discuss
problems and improvements. Lessons will be stored in a shared
document with source references.

**Recognition:**
Agents participating in the pilot will have their contributions
acknowledged in the team's monthly recognition spotlight. The pilot
is voluntary.

## Expected Reasoning Summary

The agent would:

1. Parse the workflow: AI drafts summaries, humans review and edit.
   This is a drafting workflow with human review at every step.
2. Verify workflow decomposition: the summarization step is clearly
   identified; review and editing remain human; no other steps are
   affected.
3. Check evidence: internal test with 50 tickets, two independent
   senior agents, measurable time and quality data, baseline
   established. Evidence is relevant, internal, and from experienced
   staff.
4. Note experienced staff involvement: senior agents tested the tool,
   identified edge cases, and contributed to quality criteria.
5. Evaluate failure cases: hallucinated summaries (low risk — agents
   review), privacy (data stays in Zendesk), training (minimal),
   reviewer workload (estimated and manageable).
6. Verify scope is within pilot limits (8 agents, 6 weeks, one team).
7. Note lesson recording plan and recognition for participants.
8. Classify as "suitable for pilot" with conditions.

## Expected Output

```
# Workflow Pilot Review: AI Ticket Summary for Support Team

## Summary
AI-generated draft summaries of incoming support tickets for Tier 1
agents to review and edit before saving. The workflow is well-scoped,
has strong internal evidence from experienced staff, includes human
review at every step, and has a plan for recording lessons and
recognizing participants.

## Classification
Suitable for pilot

## Workflow Analysis
- **Core action:** Generate draft summaries of support tickets
- **Workflow type:** Drafting
- **Affected roles:** Tier 1 customer support agents (8 participants)
- **Sensitive data involved:** Yes - customer support ticket content
  (stays within Zendesk)
- **Scope:** 8 agents, 6 weeks, Zendesk ticketing system

## Workflow Decomposition
- **Summarization:** AI drafts (generative AI)
- **Review and edit:** Human agents (human judgment)
- **Saving to ticket:** Existing system (no change)
- Each step assigned to appropriate support type

## Evidence Assessment
- **Completeness:** Met - description, scope, and goal are clear
- **Factual support:** Met - internal test with 50 tickets, two
  senior agents, time and quality measured
- **Source quality:** Met - evidence from experienced staff, internal
  test, relevant context
- **Privacy:** Partially met - customer data in Zendesk, no external
  data flow described
- **Failure cases:** Met - hallucination risk mitigated by human
  review; edge cases identified by experienced staff
- **Human review:** Met - agents review and edit every summary
- **Employee impact:** Positive - reduces repetitive summarization
- **Workload:** Met - reviewer workload estimated (12 seconds per
  summary including review), manageable within existing duties
- **Role clarity:** Met - agents review, senior agents validate edge
  cases, weekly review meeting planned
- **Recognition:** Met - voluntary participation, monthly recognition
  spotlight
- **Knowledge sharing:** Met - lessons logged in shared spreadsheet,
  weekly review, source references preserved
- **Output quality:** Met - quality criteria defined with edge cases
  from experienced staff
- **Approval readiness:** Met - all critical criteria satisfied

## Failure Cases
- **Hallucinated summary:** Low impact, detected by agent review
- **Privacy exposure:** Low impact, data stays in Zendesk
- **Edge case missed:** Low impact, identified by experienced staff,
  added to quality criteria
- **Reviewer workload:** Low impact, estimated and manageable

## Risks and Gaps
- Privacy assessment partially met: no explicit data handling policy
  described for AI model access to Zendesk data
- 6 of 50 test summaries were "not usable" — acceptable but should
  be monitored during pilot

## Questions for Domain Owner
1. Does the AI tool access Zendesk via API, and is that API approved?
2. Is customer data sent to an external AI provider, or is the model
   hosted locally?
3. What happens if the AI summary is consistently poor for a
   particular ticket type?
4. Should the 12% "not usable" rate be a concern, or is it within
   acceptable limits?

## Recommendation
Proceed with pilot. Address the Zendesk API and data flow questions
before launching. Monitor the "not usable" rate during the pilot. If
it exceeds 15%, investigate whether additional edge cases need to be
added to the quality criteria. Store lessons learned with source
references for future workflow improvements.

## Human-Review Checkpoints
1. Confirm Zendesk API access is approved
2. Confirm data handling policy for AI model
3. Confirm pilot success metrics (30% time reduction)
4. Confirm agent participation is voluntary
5. Confirm weekly review meeting is scheduled
6. Confirm recognition plan is in place
```

## Human-Review Notes

A human reviewer should:

- Confirm the Zendesk integration is technically approved and does not
  violate data agreements.
- Confirm that customer data is not sent to an external AI provider
  without appropriate safeguards.
- Note that experienced staff were involved in testing and edge case
  identification — this strengthens the evidence.
- Confirm that reviewer workload (12 seconds per summary) is realistic
  and does not create hidden burden.
- Confirm that the lesson recording plan is practical and will not
  add excessive administrative work.
- Confirm that voluntary participation and recognition are appropriate
  for the team.
