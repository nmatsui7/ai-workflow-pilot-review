# AI-Assisted Customer Complaint Triage — Proposal

## Organization Context

A regional utility company receives approximately 300 customer
complaints each week through email, web forms, and call-centre notes.

Customer-service employees currently read each complaint, identify
the issue category, estimate its urgency, forward it to the
appropriate department, and prepare a short acknowledgement for
the customer.

Managers report that complaints are sometimes routed inconsistently.
Employees also spend considerable time reviewing routine submissions,
while urgent complaints may not be recognized immediately.

## Current Workflow

1. A complaint is received through email, a web form, or the call
   centre.
2. A customer-service employee reads the complaint.
3. The employee selects a category from the case-management system.
4. The employee assigns an urgency level.
5. The complaint is forwarded to the responsible department.
6. The employee drafts an acknowledgement.
7. A department representative reviews the complaint and determines
   the next action.

The organization has not yet measured the average processing time or
the current rate of incorrect routing.

## Proposed AI Support

The organization proposes using an AI assistant to:

- summarize each complaint;
- suggest an issue category;
- recommend an urgency level;
- identify potentially vulnerable customers;
- suggest the department responsible for follow-up;
- draft a customer acknowledgement;
- identify similar past complaints and their resolutions.

During the pilot, employees would review all AI suggestions before
updating the case-management system or sending a response.

The AI would not automatically send messages or assign cases.

## Proposed Pilot

The organization proposes a six-week pilot involving one
customer-service team.

The pilot would initially cover:

- billing questions;
- service interruptions;
- appointment complaints;
- general service-quality complaints.

Complaints involving legal action, threats, employee misconduct,
medical concerns, or emergency situations would be excluded and
immediately escalated to existing human processes.

## Available Knowledge Sources

Potential knowledge sources include:

- complaint-category definitions;
- service-level guidelines;
- escalation procedures;
- acknowledgement templates;
- department responsibility lists;
- previous complaint records;
- past complaint resolutions;
- experienced customer-service staff.

However:

- some escalation procedures were last updated three years ago;
- complaint categories are applied inconsistently;
- previous resolutions may contain personal information;
- no one has been assigned responsibility for reviewing the AI's
  knowledge sources;
- the organization has not decided how conflicting guidance should
  be handled.

## Human-Review Proposal

Customer-service employees would review:

- the complaint summary;
- recommended category;
- urgency rating;
- routing recommendation;
- acknowledgement draft.

Employees could accept, edit, or reject each suggestion.

The proposal does not yet define:

- how much additional review time is acceptable;
- who reviews disagreements between employees and the AI;
- which errors require immediate escalation;
- whether AI suggestions should be shown before or after the
  employee forms an initial opinion;
- who remains accountable for an incorrectly prioritized complaint.

## Knowledge-Accumulation Proposal

For each reviewed complaint, the system would retain:

- the original AI recommendation;
- the employee's correction;
- the final category and urgency;
- the reason for major corrections;
- newly identified failure cases;
- references to the source complaint.

A monthly review group would examine repeated corrections and
failure cases.

Reviewed lessons could be used to update:

- category definitions;
- escalation examples;
- acknowledgement templates;
- the AI skill's reference files;
- future employee training material.

The proposal does not yet define:

- who approves a lesson for reuse;
- how personal information will be removed;
- how duplicate or conflicting lessons will be handled;
- when accumulated knowledge becomes stale;
- how incorrect guidance will be withdrawn;
- whether employees will receive recognition for identifying
  reusable improvements.

## Expected Benefits

The organization expects the pilot may:

- reduce time spent on routine classification;
- improve consistency;
- help employees identify urgent complaints;
- produce more consistent acknowledgements;
- make recurring complaint patterns easier to identify;
- capture experienced employees' knowledge for future use.

These benefits have not yet been measured or validated.

## Possible Risks

Potential risks include:

- an urgent complaint being rated as routine;
- sensitive personal information being exposed through past-case
  retrieval;
- employees becoming anchored to incorrect AI recommendations;
- inconsistent or outdated escalation guidance;
- generic acknowledgements that do not fit the customer's situation;
- increased employee workload due to reviewing and documenting AI
  errors;
- managers treating AI recommendations as more reliable than employee
  judgment;
- employee corrections being used to improve the process without
  recognition;
- unreviewed lessons being promoted into reusable guidance;
- customers assuming that an AI-generated acknowledgement represents
  a final decision.

## Proposed Success Measures

The project team suggests measuring:

- average complaint-processing time;
- routing accuracy;
- urgency-classification accuracy;
- number of employee corrections;
- acknowledgement revision rate;
- reviewer time;
- number and severity of missed exceptions;
- employee confidence in the workflow;
- number of reviewed lessons added to the knowledge base.

No baseline measurements have been completed.

## Proposed Stop or Revision Conditions

The pilot should stop or be revised if:

- a serious complaint is incorrectly deprioritized;
- sensitive information is exposed;
- employees consistently spend more time reviewing than the workflow
  saves;
- routing accuracy declines;
- the AI repeatedly ignores documented exceptions;
- staff report that the workflow undermines their judgment;
- accumulated lessons are reused without review;
- no accountable owner is available.

## Requested Review

Evaluate whether this proposal should be classified as:

- Candidate for limited pilot
- Needs further discovery
- Needs governance or policy review
- Not currently suitable
- Reject due to excessive risk or autonomy

Identify:

- evidence gaps;
- workflow-design concerns;
- required knowledge sources;
- failure cases;
- human-review requirements;
- adoption risks;
- pilot-readiness issues;
- knowledge-accumulation strengths and gaps;
- questions that must be answered by the domain owner.
