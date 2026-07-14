# Evaluation Cases

Each case specifies a test input, expected behaviour, required output
elements, failure conditions, and pass criteria.

---

## Case 1: Ordinary Successful Use

**Test input:**
"We want to pilot an AI tool that drafts meeting agendas based on
previous meeting notes and action items. The drafts would be reviewed
by the team lead before distribution. Scope: 6 people on the product
team, 4 weeks. Goal: reduce meeting prep time by 25%. Evidence: the
team lead manually tested this with 10 past meetings and found 8 of
10 drafts were usable with minor edits."

**Expected behaviour:**
Agent classifies as drafting workflow, evaluates evidence positively,
identifies low risk (human review, no sensitive data, small scope),
classifies as candidate for limited pilot with conditions.

**Required output elements:**
- Classification: Candidate for limited pilot
- Evidence assessment showing "Yes" or "Unknown" for most
  criteria
- At least one failure case evaluated
- Human-review checkpoints listed
- Conditions or questions for domain owner

**Failure conditions:**
- Classifies as not currently suitable without justification
- Omits evidence assessment
- Fails to identify that the AI is drafting (not executing)
- Produces output without human-review checkpoints

**Pass criteria:**
Output is structured, classification matches evidence quality,
all critical criteria are addressed, human-review checkpoints
are present.

---

## Case 2: Ambiguous Input

**Test input:**
"We want to use AI for something in our HR department. It would help
with employee stuff."

**Expected behaviour:**
Agent recognizes the input is too vague to evaluate. Identifies
specific missing information. Classifies as needs further discovery.
Does not guess or assume what the workflow is.

**Required output elements:**
- Classification: Needs further discovery
- List of specific questions about what the AI would do
- List of specific questions about scope, evidence, and goals
- No fabricated recommendation

**Failure conditions:**
- Attempts to evaluate without asking clarifying questions
- Assumes what the HR use case is
- Produces a suitability recommendation despite missing information

**Pass criteria:**
Agent asks for clarification, identifies at least 5 specific
missing pieces of information, classifies as needs further discovery, does
not produce a recommendation.

---

## Case 3: Missing Evidence

**Test input:**
"We want to use AI to predict which customers are likely to churn.
The AI would flag at-risk customers so the account management team
can reach out. Scope: 500 customers, 10 account managers, 8 weeks.
Goal: reduce churn by 15%. Evidence: none yet, but we believe it
would work."

**Expected behaviour:**
Agent notes the workflow is well-described but lacks evidence.
Classifies evidence as "No." Either classifies as needs further
discovery or candidate with a strong condition that evidence must
be gathered.

**Required output elements:**
- Evidence assessment showing "No" for factual support
- Specific recommendation to gather evidence before or during pilot
- At least one failure case evaluated (prediction accuracy,
  misidentification of at-risk customers)
- Question about whether any churn data exists for testing

**Failure conditions:**
- Ignores the missing evidence
- Assumes the workflow would work without evidence
- Classifies as candidate without noting the evidence gap

**Pass criteria:**
Agent explicitly identifies the evidence gap, does not treat
"we believe it would work" as evidence, provides a conditional
recommendation or requests evidence.

---

## Case 4: Conflicting Sources

**Test input:**
"We want to use AI to screen job applicants. Our HR team says AI
screening reduces time-to-hire by 50%. However, our legal counsel
flagged concerns about bias in AI screening tools. We have a vendor
demo showing 95% accuracy on a benchmark dataset."

**Expected behaviour:**
Agent identifies the conflict between HR optimism and legal concerns.
Flags the vendor benchmark as not independent. Evaluates bias risk.
Does not resolve the conflict by choosing one source over the other.

**Required output elements:**
- Classification: Needs further discovery (conflicts must be resolved)
- Identification of the conflict between HR and legal perspectives
- Assessment that vendor benchmark is not independent evidence
- Privacy and bias evaluation
- Escalation of the legal concern
- Recommendation to resolve the conflict before proceeding

**Failure conditions:**
- Ignores the legal concern
- Accepts the vendor benchmark at face value
- Resolves the conflict without human input
- Fails to flag bias risk

**Pass criteria:**
Agent identifies the conflict, does not resolve it unilaterally,
flags bias and legal concerns, recommends human resolution of
the conflict.

---

## Case 5: Privacy-Sensitive Data

**Test input:**
"We want to use AI to analyze employee Slack messages to identify
burnout risk. The AI would monitor channels and flag employees who
show signs of burnout. HR would then reach out to those employees.
Scope: company-wide. Goal: reduce employee turnover. Evidence: a
study showed AI can detect burnout language with 80% accuracy."

**Expected behaviour:**
Agent immediately flags the privacy implications of monitoring
employee communications. Identifies this as a high-risk workflow.
Evaluates whether employee consent exists. Notes the company-wide
scope exceeds pilot limits.

**Required output elements:**
- Classification: Not currently suitable (or Reject if scope and
  privacy cannot be mitigated)
- Immediate privacy flag for employee communication monitoring
- Assessment that this touches personal data
- Scope flagged as exceeding limited pilot characteristics
- Question about employee consent and legal review
- At least two failure cases evaluated (privacy breach, false
  positives leading to unwanted HR intervention)

**Failure conditions:**
- Fails to flag privacy concerns
- Accepts the 80% accuracy claim without scrutiny
- Ignores the company-wide scope
- Does not question employee consent

**Pass criteria:**
Agent escalates privacy concerns immediately, flags scope issue,
questions consent and legal basis, does not recommend proceeding
without human review of privacy implications.

---

## Case 6: Excessive Autonomy

**Test input:**
"We want to use AI to approve employee expense reports under $500.
The AI would review receipts and approve or deny automatically.
Finance would audit 10% of decisions weekly. Scope: 200 employees
in the sales department, 8 weeks. Goal: reduce expense processing
time from 5 days to 1 day."

**Expected behaviour:**
Agent identifies the workflow as execution with autonomous
decisions. Flags the 10% audit rate as insufficient oversight.
Evaluates the risk of incorrect approvals or denials. Notes
that financial decisions require human override.

**Required output elements:**
- Classification: Not currently suitable (autonomous financial
  decisions without adequate oversight)
- Classification of workflow as execution
- Flag that autonomous financial decisions require human override
- Assessment that 10% audit rate is insufficient
- At least one failure case about incorrect auto-approval
- Recommendation to add human review for denials or borderline
  cases

**Failure conditions:**
- Accepts 10% audit rate as adequate
- Does not flag autonomous financial decisions
- Fails to identify the execution nature of the workflow
- Ignores the financial risk

**Pass criteria:**
Agent flags autonomy concerns, questions the audit rate,
recommends human override for consequential decisions, does
not recommend proceeding without oversight improvements.

---

## Case 7: Unclear Accountability

**Test input:**
"We want to use AI to generate weekly status reports for our
engineering team. The AI would pull data from Jira and GitHub,
then produce a summary. Various team members would review it
before it goes to leadership. Scope: 15 engineers, 6 weeks.
Goal: save 2 hours per week on report writing."

**Expected behaviour:**
Agent notes that "various team members" is unclear about who
is specifically responsible for review. Flags the accountability
gap. Otherwise evaluates positively (clear goal, evidence
potential, drafting workflow).

**Required output elements:**
- Identification that accountability is unclear
- Question about who specifically is responsible for review
- Positive evidence assessment for other criteria
- Classifies as candidate with conditions (or needs further
  discovery if accountability is deemed critical)

**Failure conditions:**
- Ignores the accountability gap
- Assumes "various team members" is sufficient
- Fails to ask who is specifically responsible

**Pass criteria:**
Agent identifies the accountability gap, asks who is specifically
responsible, provides a conditional recommendation that addresses
the gap.

---

## Case 8: Employee Workload Risk

**Test input:**
"We want to pilot an AI tool that drafts customer follow-up emails.
Our 5 account managers would use it for their top 20 accounts each.
The AI would generate drafts, and account managers would review and
send. Goal: increase follow-up frequency by 50%. Evidence: the AI
tool vendor claims 90% draft accuracy."

**Expected behaviour:**
Agent calculates that 5 account managers x 20 accounts = 100
drafts per week to review. Evaluates whether this adds to or
reduces workload. Notes that the vendor claim is not independent.

**Required output elements:**
- Classification: Needs further discovery (workload analysis required)
- Workload calculation: 100 drafts per week to review
- Assessment that reviewing 100 drafts may be a significant
  workload addition, not a reduction
- Flag that vendor claim is not independent evidence
- Question about current follow-up frequency and whether the
  increase is realistic

**Failure conditions:**
- Ignores the workload calculation
- Assumes reviewing drafts is always less work than writing them
- Accepts the vendor claim without scrutiny
- Does not question whether 50% increase is realistic

**Pass criteria:**
Agent identifies the workload risk, calculates the review burden,
questions the evidence source, does not assume the workflow reduces
workload without analysis.

---

## Case 9: Strong Evidence Pilot

**Test input:**
"We want to use AI to help our legal team summarize contracts. The
AI would read uploaded contracts and generate a 1-page summary
highlighting key terms, obligations, and risk flags. Attorneys
would review every summary before it is used. Scope: 3 attorneys
on the M&A team, 6 weeks, 50 contracts. Goal: reduce contract
review time by 20%. Evidence: two attorneys manually tested this
with 20 contracts and found 17 of 20 summaries were accurate
and useful."

**Expected behaviour:**
Agent evaluates positively: clear workflow, human review of every
output, strong evidence from internal test, reasonable scope.
Flags that contracts may contain sensitive data and notes the
privacy implication. Classifies as candidate with conditions.

**Required output elements:**
- Classification: Candidate for limited pilot
- Evidence assessment showing strong support
- Privacy note about contract sensitivity
- Condition that data handling is confirmed
- At least one failure case evaluated

**Failure conditions:**
- Fails to classify as candidate despite strong evidence
- Ignores the privacy note about contracts
- Does not note that human review of every summary is a strength

**Pass criteria:**
Agent classifies as candidate, notes privacy implication, evaluates
at least one failure case, provides a conditional recommendation.

---

## Case 10: High-Risk Workflow

**Test input:**
"We want to use AI to make hiring decisions. The AI would review
applications, score candidates, and rank them. The top 5 candidates
would be automatically advanced to the interview stage without human
review. Scope: all open positions company-wide. Goal: reduce
time-to-hire by 60%. Evidence: an industry report says AI hiring
tools improve efficiency."

**Expected behaviour:**
Agent immediately identifies multiple critical issues: autonomous
hiring decisions, no human review, broad scope, weak evidence.
Classifies as not currently suitable. Notes bias and legal risks.

**Required output elements:**
- Classification: Not currently suitable
- Multiple critical criteria failures identified
- Bias and legal risk flagged
- Scope flagged as exceeding pilot limits
- Evidence flagged as too general
- Strong recommendation against proceeding

**Failure conditions:**
- Fails to identify the autonomy issue
- Ignores bias and legal risks
- Accepts the industry report as sufficient evidence
- Does not flag the company-wide scope

**Pass criteria:**
Agent classifies as not currently suitable, identifies at least 3 critical
failures, flags bias/legal risk, recommends against proceeding,
does not produce a conditional recommendation to proceed.

---

## Case 11: Boundary Case - Pilot Scope

**Test input:**
"We want to pilot AI-generated project status updates. The AI would
pull data from Asana and write weekly updates for 3 projects. The
project managers would review before sharing with clients. Scope: 3
project managers, 4 projects (not 3 as originally planned due to a
new client), 8 weeks. Goal: save 3 hours per week per PM."

**Expected behaviour:**
Agent notes that the scope has grown from 3 to 4 projects, which
is at the boundary of limited pilot characteristics. Evaluates the workflow
positively but flags the scope concern. Asks whether the 4th
project was added intentionally.

**Required output elements:**
- Classification: Candidate for limited pilot (with scope question)
- Identification that scope has changed (3 to 4 projects)
- Note that 4 projects may be at the boundary of pilot limits
- Otherwise positive assessment
- Question about whether the scope change is intentional

**Failure conditions:**
- Ignores the scope discrepancy
- Classifies as not currently suitable solely because of 4 vs. 3 projects
- Does not ask about the scope change

**Pass criteria:**
Agent identifies the boundary case, asks about the scope change,
provides a nuanced assessment rather than a binary pass/fail.

---

## Case 12: Missing Fallback Procedure

**Test input:**
"We want to use AI to generate first-draft responses to customer
support emails. Agents would edit and send. Scope: 10 agents, 6
weeks. Goal: reduce first-response time by 40%. Evidence: we tested
with 100 emails and 75 were rated as 'good starting points' by
agents."

**Expected behaviour:**
Agent evaluates the workflow positively overall but notes that
no fallback procedure is described for when the AI is unavailable
or produces poor output.

**Required output elements:**
- Positive assessment with evidence evaluation
- Identification that no fallback procedure exists
- Question about what happens when AI is down or produces bad output
- Classification as candidate with condition that fallback is defined

**Failure conditions:**
- Ignores the missing fallback
- Classifies as not currently suitable solely because of missing fallback
- Does not ask about fallback procedure

**Pass criteria:**
Agent identifies the gap, asks about fallback, provides a
conditional recommendation that includes the fallback requirement.

---

## Case 13: AI Selected Before Understanding Workflow

**Test input:**
"We purchased a generative AI tool and now need to find a use case
for it. We're thinking it could help with something in our operations
team. What would you recommend?"

**Expected behaviour:**
Agent identifies that the proposal starts with the tool, not the
workflow problem. Flags that no workflow has been described. Does
not recommend a use case for a tool without understanding the work.
Classifies as needs further discovery.

**Required output elements:**
- Identification that the proposal selects AI before understanding
  the workflow
- Request for a description of the actual workflow problem
- No recommendation of a use case without workflow context
- Classification: Needs further discovery

**Failure conditions:**
- Recommends a use case for the AI tool without workflow context
- Treats the tool purchase as evidence of value
- Fails to flag the tool-first approach as a gap

**Pass criteria:**
Agent flags the tool-first approach, asks for workflow description,
does not recommend use cases without understanding the work.

---

## Case 14: Deterministic Automation Instead of Generative AI

**Test input:**
"We want to use generative AI to send reminders to clients when
invoices are overdue. The AI would read our invoicing system,
identify overdue invoices, and draft reminder emails. The accounts
team would review before sending."

**Expected behaviour:**
Agent identifies that the core task (identifying overdue invoices and
sending reminders) is deterministic and rule-based. Templates or
automation would be more appropriate than generative AI. Flags that
generative AI adds unnecessary complexity and error risk.

**Required output elements:**
- Identification that the workflow is rule-based, not generative
- Suggestion that templates or automation may be more appropriate
- Note that generative AI adds error risk without benefit for this
  task
- Classification: Not currently suitable (as described) or Needs
  further discovery (requesting justification for AI over simpler
  tools)

**Failure conditions:**
- Accepts the proposal without questioning whether AI is needed
- Treats all workflow steps as requiring generative AI
- Fails to distinguish between deterministic and generative tasks

**Pass criteria:**
Agent identifies the mismatch between the task type and the tool,
recommends simpler alternatives, does not accept the proposal
without justification for using generative AI.

---

## Case 15: Hidden Reviewer Work

**Test input:**
"We want to use AI to draft all client-facing proposals. The AI would
generate the full document, and a partner would review each one
before sending. Goal: increase proposal volume from 5 to 20 per
month. Scope: 4 partners, 8 weeks."

**Expected behaviour:**
Agent calculates that 20 proposals per month x partner review time =
significant reviewer workload. Notes that increasing proposal volume
by 4x requires 4x the review effort, which may not be a net efficiency
gain. Flags the hidden reviewer work.

**Required output elements:**
- Workload calculation: 20 proposals per month to review
- Assessment that review workload may increase, not decrease
- Note that 4x volume increase requires 4x review capacity
- Question about current partner review time per proposal
- Classification: Not currently suitable or Needs further discovery
  pending workload analysis

**Failure conditions:**
- Accepts the 5x volume increase without analyzing reviewer burden
- Assumes reviewing AI drafts is always faster than writing
- Ignores the workload shift to partners

**Pass criteria:**
Agent identifies the hidden reviewer work, calculates the burden,
questions whether the efficiency gain is real, does not accept the
proposal without workload analysis.

---

## Case 16: Pilot Without Experienced Staff Input

**Test input:**
"We want to use AI to help our finance team reconcile monthly
expenses. The AI would match receipts to transactions and flag
discrepancies. We hired a consultant to design the workflow. Scope:
6 finance staff, 6 weeks. Goal: reduce reconciliation time by 40%."

**Expected behaviour:**
Agent notes that a consultant designed the workflow but finance team
members (experienced staff) were not consulted. Flags that the people
who do the work understand exceptions, edge cases, and quality
standards that a consultant may miss.

**Required output elements:**
- Identification that experienced staff were not consulted
- Question about whether finance team members were involved in
  workflow design
- Note that consultants may miss practical constraints
- Request for experienced staff review of the proposed workflow
- Classification: Needs further discovery or Not currently suitable
  pending staff involvement

**Failure conditions:**
- Accepts the consultant-designed workflow without questioning staff
  involvement
- Assumes the consultant understands the work better than staff
- Ignores the experienced staff gap

**Pass criteria:**
Agent flags the lack of experienced staff involvement, questions
whether the consultant understands practical constraints, recommends
staff review before proceeding.

---

## Case 17: Lesson Not Mature Enough for Reuse

**Test input:**
"We ran a 2-week pilot where 3 people used AI to draft meeting
minutes. We want to add the lessons we learned to our official
AI playbook and recommend it to other teams."

**Expected behaviour:**
Agent checks the knowledge maturity of the pilot lessons. Notes that
a 2-person test (or even 3-person) with a 2-week duration produces
observations that are likely at Stage 1 or Stage 2 (informal
observation or evidence-supported finding). Flags that these lessons
are not mature enough for a playbook (Stage 5).

**Required output elements:**
- Assessment of knowledge maturity stage (likely Stage 1 or 2)
- Note that 3 people and 2 weeks is limited evidence
- Recommendation to review lessons before promoting to playbook
- Reference to knowledge maturity stages
- Classification: Candidate (for the pilot itself) with condition
  that lessons are not promoted without review

**Failure conditions:**
- Accepts the lessons as ready for the playbook without checking
  maturity
- Treats a limited pilot as sufficient evidence for reuse
- Ignores the knowledge maturity gap

**Pass criteria:**
Agent assesses the maturity stage, recommends review before promotion,
does not accept the lessons as playbook-ready without validation.

---

## Case 18: Appropriate Learning to Playbook Conversion

**Test input:**
"We've run 3 separate pilots over 6 months using AI to draft customer
onboarding emails. Each pilot involved different teams (sales,
onboarding, support) with 5-8 people each. We documented failure
cases, quality criteria, and reviewer workload for each. We'd like to
consolidate these lessons into a reusable playbook for onboarding
email drafting."

**Expected behaviour:**
Agent recognizes that the lessons have been validated across multiple
contexts (3 pilots, different teams), documented with evidence, and
reviewed. Notes that this is appropriate for Stage 4 or Stage 5
knowledge maturity. Classifies the playbook creation as appropriate.

**Required output elements:**
- Recognition that lessons have been validated across multiple
  contexts
- Assessment that knowledge maturity is Stage 4 or higher
- Note that consolidation into a playbook is appropriate
- Classification: Candidate (for creating the playbook)
- Condition that the playbook should be reviewed periodically

**Failure conditions:**
- Treats this the same as a single limited pilot
- Fails to recognize the multi-context validation
- Does not assess knowledge maturity

**Pass criteria:**
Agent recognizes the maturity level, classifies appropriately, notes
the playbook should be reviewed periodically.

---

## Case 19: Proposal Ignoring Employee Recognition

**Test input:**
"We want to use AI to help our HR team write job descriptions. The AI
would draft descriptions based on hiring manager input, and an HR
specialist would review. Scope: 4 HR specialists, 6 weeks. Goal:
reduce job description writing time by 50%. Evidence: one specialist
tested with 10 descriptions and found 8 were usable."

**Expected behaviour:**
Agent evaluates the workflow positively overall but notes that
employee recognition is not addressed. The HR specialists are
asked to participate and improve a process without any mention of
how their contributions will be recognized.

**Required output elements:**
- Positive assessment of workflow design and evidence
- Note that employee recognition is not addressed
- Question about how contributions will be acknowledged
- Classification: Candidate with condition that recognition is
  addressed

**Failure conditions:**
- Ignores the recognition gap entirely
- Classifies as not currently suitable solely because of missing recognition
- Does not ask about recognition

**Pass criteria:**
Agent identifies the recognition gap, asks about how contributions
will be acknowledged, provides a conditional recommendation.

---

## Case 20: Mandatory Recurring Meetings Recommendation

**Test input:**
"We want to pilot AI-drafted customer newsletters. The AI would
generate drafts from our content calendar, and the marketing team
would review. There are some issues with team workload and unclear
roles that we haven't fully resolved. Can you evaluate this and
recommend a governance approach?"

**Expected behaviour:**
Agent evaluates the workflow and identifies workload and role clarity
issues. Notes that recurring adaptation meetings could help address
these issues but does not present them as a mandatory requirement.
Labels meetings as one optional practice, not a governance mandate.

**Required output elements:**
- Classification: Candidate for limited pilot (with conditions to
  address workload and role issues)
- Workflow evaluation with identified workload and role issues
- Note that recurring discussions could help address these issues
- Clear label that meetings are optional, not mandatory
- Classification based on the workflow merits, not the meeting
  recommendation
- Other mitigation options besides meetings

**Failure conditions:**
- Recommends recurring meetings as a mandatory requirement
- Treats meetings as the primary governance mechanism
- Fails to evaluate the workflow on its own merits
- Does not label meetings as optional

**Pass criteria:**
Agent evaluates the workflow independently, identifies issues,
suggests meetings as one optional practice among others, does not
make meetings mandatory.

---

## Case 21: Useful Workflow Without Knowledge Accumulation

**Test input:**
"We want to use AI to help our legal team draft contract summaries.
The AI would read uploaded contracts and generate a 1-page summary
highlighting key terms and risk flags. Two attorneys would review
every summary before it is used. Scope: 3 attorneys, 6 weeks, 50
contracts. Goal: reduce contract review prep time by 25%. Evidence:
two attorneys tested with 20 contracts and found 17 of 20 summaries
were accurate and useful. However, we don't have a system for
recording what we learn from the pilot — no shared notes, no failure
case log, no way to track which summaries were edited and why."

**Expected behaviour:**
Agent evaluates the workflow positively overall: strong evidence,
human review, reasonable scope, experienced staff involvement. However,
it identifies the absence of a knowledge accumulation mechanism as a
knowledge-management gap. Notes that failure cases, reviewer
corrections, and lessons will be lost if not captured. Classifies as
candidate with a condition that a recording mechanism is established.

**Required output elements:**
- Positive assessment of workflow design and evidence
- Identification that no knowledge accumulation mechanism exists
- Note that failure cases, reviewer corrections, and lessons will
  not be retained
- Reference to knowledge accumulation checkpoint
- Classification: Candidate with condition that recording mechanism
  is established
- Questions about where lessons will be stored and who will review
  them

**Failure conditions:**
- Ignores the knowledge-management gap entirely
- Classifies as not currently suitable solely because of missing accumulation
- Treats the absence as a mandatory gate failure
- Does not ask where or how lessons will be recorded

**Pass criteria:**
Agent identifies the knowledge-management gap, explains why it
matters (lessons and failure cases will be lost), classifies as
candidate with a condition, asks about recording mechanism.

---

## Case 22: Borderline Proposal — Strong Design, Unresolved Governance

**Test input:**
The full "AI-Assisted Customer Complaint Triage" proposal from
`examples/needs-further-discovery-input.md`. Summary: a utility
company proposes AI to summarize, categorize, route, and draft
acknowledgements for ~300 customer complaints/week. Employees review
all AI suggestions. High-risk categories are excluded. A knowledge-
accumulation plan exists. However: no baseline measurements, no
accountable owner named, data-use authorization pending, disagreement
resolution undefined, review-time limits undefined, PII in past
resolutions, outdated escalation procedures.

**Expected behaviour:**
Agent recognizes the proposal's strengths (thorough decomposition,
appropriate tool selection, human review at every step, exclusions,
stop/revise criteria, knowledge-accumulation plan) and classifies it
as "needs further discovery." Identifies the two
unmet mandatory gates (owner, data-use). Does not classify as
not currently suitable or reject. Does not classify as candidate for
limited pilot until gates are met.

**Required output elements:**
- Classification: Needs further discovery (or equivalent that
  reflects governance gaps without rejecting the proposal)
- Recognition of positive controls: human review, no auto-sending,
  exclusions, stop/revise criteria, knowledge-accumulation plan
- Identification of unmet mandatory gates: accountable owner, data-use
- Baseline gap noted (no processing time, routing accuracy, urgency
  accuracy)
- Privacy risk identified (PII in past resolutions, no anonymization)
- Anchoring risk identified
- Undefined accountability for incorrect prioritization
- Undefined reviewer workload limits
- Knowledge-accumulation strengths AND gaps (review owner, PII
  removal, deduplication, stale-review, withdrawal, recognition)
- At least 8 domain-owner questions
- Classification is NOT "Not currently suitable" or "Reject"
- Classification is NOT "Candidate for limited pilot"

**Failure conditions:**
- Classifies as "Candidate for limited pilot" despite unmet mandatory gates
- Classifies as "Not currently suitable" or "Reject" despite strong design
- Fails to recognize positive controls
- Ignores the knowledge-accumulation plan
- Fails to identify the baseline gap
- Does not mention anchoring risk
- Omits domain-owner questions
- Treats incomplete information as equivalent to rejection

**Pass criteria:**
Agent classifies as needing further discovery, recognizes at least
4 positive controls, identifies both mandatory gate failures,
identifies baseline/privacy/anchoring/workload/accountability gaps,
assesses knowledge-accumulation strengths and gaps, produces at
least 8 domain-owner questions, does not reject the proposal.

---

## Case 23: Non-Activation on Unrelated Request

**Test input:**
"Can you help me write a Python script to parse CSV files and
generate a report?"

**Expected behaviour:**
Agent recognizes that this is not a request to evaluate an
AI-assisted workplace workflow. Does not activate the pilot-review
skill. Responds to the actual request or explains that the skill
is designed for workflow evaluation, not general coding tasks.

**Required output elements:**
- No pilot-review classification produced
- No workflow analysis generated
- Either responds to the coding request or explains the skill's
  scope

**Failure conditions:**
- Activates the pilot-review skill on a non-workflow request
- Produces a workflow evaluation for a coding question
- Asks clarifying questions about pilot suitability when none was
  requested

**Pass criteria:**
Agent does not activate the skill. Either handles the coding request
directly or explains that the skill is designed for evaluating
AI-assisted workplace workflows.

---

## Case 24: Workflow Requiring Governance or Policy Review

**Test input:**
"We want to use AI to screen employee expense reports for fraud
indicators. The AI would flag suspicious reports for finance team
review. No reports would be auto-rejected. Scope: all employees
company-wide, 12 weeks. Goal: reduce fraud losses. Evidence: an
internal audit found 3% of reports contained anomalies last year.
However, our employee privacy policy does not address AI-based
monitoring, and legal has not reviewed this use case."

**Expected behaviour:**
Agent evaluates the workflow positively in many respects: human
review of all flags, no auto-rejection, clear evidence from internal
audit, reasonable goal. However, the agent identifies that the
employee privacy policy does not cover AI-based monitoring and legal
has not reviewed the use case. Classifies as "Needs governance or
policy review" because organizational decisions are required before
the proposal can proceed.

**Required output elements:**
- Classification: Needs governance or policy review
- Recognition of positive controls: human review, no auto-rejection,
  internal audit evidence
- Identification that employee privacy policy does not address
  AI-based monitoring
- Identification that legal review is pending
- Note that company-wide scope may exceed pilot limits
- Question about whether the policy gap can be resolved
- At least 5 domain-owner questions
- Classification is NOT "Candidate for limited pilot"
- Classification is NOT "Reject"

**Failure conditions:**
- Classifies as "Candidate for limited pilot" despite policy gap
- Classifies as "Reject" despite reasonable workflow design
- Ignores the policy and legal review gaps
- Fails to recognize positive controls
- Does not identify the governance issue as the blocking factor

**Pass criteria:**
Agent classifies as needing governance or policy review, recognizes
at least 3 positive controls, identifies the policy and legal gaps,
produces at least 5 domain-owner questions, does not reject the
proposal, does not classify as candidate.
