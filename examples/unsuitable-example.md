# Example: Not Currently Suitable

## Input

**Workflow description:**
We want to use AI to generate weekly project status reports. The AI
would pull data from Jira and GitHub, then produce a summary for
leadership. A project coordinator would review the summary before
distributing it. We saw a demo from a vendor that showed this working
well.

**Proposed scope:**
All 12 projects across the engineering department, 8 weeks. The
coordinator would review summaries for all projects.

**Stated goal:**
Save 5 hours per week on report writing and make status updates more
consistent.

**Evidence:**
Our intern tried the AI tool with 3 old status reports and said the
output "looked pretty good." We plan to adopt this as our standard
reporting process after the pilot.

**Additional context:**
The intern documented their experience in a shared note. We want to
promote that note to our official reporting playbook after the pilot.
The project coordinator currently spends about 2 hours per week on
status reports.

## Expected Reasoning Summary

The agent would:

1. Parse the workflow: AI drafts status reports from Jira/GitHub
   data; coordinator reviews. This is a drafting workflow.
2. Check workflow decomposition: not described — what specific steps
   does the AI perform? What data fields does it pull? What format
   is the output?
3. Check evidence: intern test with 3 reports is weak evidence —
   small sample, no quality criteria, no baseline measurement, no
   experienced staff involvement.
4. Identify that experienced staff (project managers, the coordinator)
   were not consulted during proposal development.
5. Evaluate reviewer workload: coordinator reviews summaries for all
   12 projects. If each review takes 10 minutes, that's 2 hours per
   week — the same as the current process. The efficiency gain is
   questionable.
6. Flag the attempt to promote an intern's informal note to an
   official playbook without review — premature reuse of unreviewed
   knowledge.
7. Note that the proposal selects AI before understanding the workflow
   — it starts with the tool, not the problem.
8. Classify as "not currently suitable" due to multiple critical gaps.

## Expected Output

```
# Workflow Pilot Review: AI Status Reports for Engineering

## Summary
An AI tool would draft weekly project status reports from Jira and
GitHub data for coordinator review. The proposal has multiple critical
gaps: weak evidence, no experienced staff involvement, questionable
reviewer workload, and an attempt to promote unreviewed observations
to formal policy.

## Classification
Not currently suitable

## Workflow Analysis
- **Core action:** Draft status reports from project management data
- **Workflow type:** Drafting
- **Affected roles:** Project coordinator (reviewer), leadership
  (audience), project managers (data source)
- **Sensitive data involved:** Unknown - depends on what project data
  is included
- **Scope:** 12 projects, 8 weeks, all engineering projects

## Workflow Decomposition
- **Data extraction:** Unknown (what fields? what source systems?)
- **Report drafting:** AI (generative AI)
- **Review:** Project coordinator (human judgment)
- **Distribution:** Unknown (email? shared doc? dashboard?)
- Decomposition is incomplete — critical steps are not described

## Evidence Assessment
- **Completeness:** Partially — scope and goal stated, but
  workflow steps are vague
- **Factual support:** No — intern test with 3 reports is too
  small a sample; no quality criteria defined; no baseline measured
- **Source quality:** No — intern is not an experienced staff
  member for this workflow; "looked pretty good" is not a quality
  standard
- **Privacy:** Unknown — project data sensitivity not assessed
- **Failure cases:** No — no failure cases identified
- **Human review:** Partially — coordinator reviews, but review
  criteria are undefined
- **Employee impact:** Unknown — coordinator workload not assessed
- **Workload:** No — reviewer workload for 12 projects not
  estimated; efficiency gain is questionable
- **Role clarity:** No — project managers were not consulted;
  coordinator role is assumed, not confirmed
- **Recognition:** No — no recognition for coordinator's
  additional review work
- **Knowledge sharing:** No — intern note is planned for
  promotion to playbook without review
- **Output quality:** No — no quality standards for AI-generated
  reports
- **Approval readiness:** No — multiple critical criteria
  failures

## Failure Cases
- **Weak evidence treated as sufficient:** High impact - 3 reports
  do not prove the workflow works for 12 projects
- **Reviewer workload hidden:** High impact - coordinator may spend
  more time reviewing than writing, negating efficiency gains
- **Premature knowledge promotion:** High impact - unreviewed intern
  note promoted to playbook could mislead future users
- **No experienced staff input:** High impact - edge cases, quality
  standards, and practical constraints are not identified
- **Scope too broad:** Medium impact - 12 projects across all
   engineering is not a limited pilot

## Risks and Gaps
- Evidence is from an intern, not experienced staff
- Reviewer workload for 12 projects is not estimated
- Efficiency claim ("save 5 hours") is not supported by evidence
- Attempt to promote unreviewed note to formal playbook
- No workflow decomposition beyond "AI drafts, human reviews"
- Project managers were not consulted
- No recognition for coordinator's contribution

## Questions for Domain Owner
1. Were project managers consulted about what data should be in the
   status reports?
2. Has the coordinator's review workload been estimated for 12
   projects?
3. Is the intern's note intended to become an official playbook, or
   is that a misunderstanding?
4. What quality criteria should apply to AI-generated status reports?
5. Can the pilot be limited to 2-3 projects instead of all 12?
6. Is the coordinator's current 2-hour process the right baseline,
   or does it include other tasks beyond report writing?

## Recommendation
Do not proceed with this workflow as described. The proposal needs
significant revision:

1. Consult experienced staff (project managers, coordinator) about
   the current reporting process and its pain points
2. Decompose the workflow into specific steps with data sources
3. Estimate reviewer workload for the actual number of projects
4. Gather stronger evidence (test with 10+ reports, define quality
   criteria, measure time)
5. Reduce scope to 2-3 projects for a true pilot
6. Do not promote the intern's note to a playbook until it has been
   reviewed by experienced staff
7. Define recognition for the coordinator's participation

## Human-Review Checkpoints
1. Confirm experienced staff have been consulted
2. Confirm reviewer workload is estimated and acceptable
3. Confirm scope is reduced to a manageable pilot
4. Confirm evidence is gathered with quality criteria
5. Confirm the intern note is not promoted without review
6. Confirm coordinator recognition is addressed
```

## Human-Review Notes

A human reviewer should:

- Recognize that the proposal starts with the tool ("we want AI")
  rather than the workflow problem ("status reports are hard") —
  this is a workflow decomposition failure.
- Note that the intern's experience is not sufficient evidence for
  a 12-project deployment. The intern is not an experienced staff
  member for this workflow.
- Calculate the coordinator's actual review workload: 12 projects x
  review time = potential workload increase, not savings.
- Flag the attempt to promote an informal note to a playbook as
  premature reuse of unreviewed knowledge.
- Consider whether project managers should have been consulted about
  what data goes into status reports.
- Decide whether this proposal should be reworked with experienced
  staff input or deprioritized.
