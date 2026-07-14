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
classifies as suitable for pilot with conditions.

**Required output elements:**
- Classification: Suitable for pilot
- Evidence assessment showing "Met" or "Partially met" for most
  criteria
- At least one failure case evaluated
- Human-review checkpoints listed
- Conditions or questions for domain owner

**Failure conditions:**
- Classifies as unsuitable without justification
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
specific missing information. Classifies as incomplete. Does not
guess or assume what the workflow is.

**Required output elements:**
- Classification: Incomplete
- List of specific questions about what the AI would do
- List of specific questions about scope, evidence, and goals
- No fabricated recommendation

**Failure conditions:**
- Attempts to evaluate without asking clarifying questions
- Assumes what the HR use case is
- Produces a suitability recommendation despite missing information

**Pass criteria:**
Agent asks for clarification, identifies at least 5 specific
missing pieces of information, classifies as incomplete, does
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
Classifies evidence as "Not met." Either classifies as incomplete
or suitable with a strong condition that evidence must be gathered.

**Required output elements:**
- Evidence assessment showing "Not met" for factual support
- Specific recommendation to gather evidence before or during pilot
- At least one failure case evaluated (prediction accuracy,
  misidentification of at-risk customers)
- Question about whether any churn data exists for testing

**Failure conditions:**
- Ignores the missing evidence
- Assumes the workflow would work without evidence
- Classifies as suitable without noting the evidence gap

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
- Immediate privacy flag for employee communication monitoring
- Assessment that this touches personal data
- Scope flagged as exceeding small pilot limits
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
- Classification as suitable with conditions (or incomplete if
  accountability is deemed critical)

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

## Case 9: Suitable Small Pilot

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
privacy implication. Classifies as suitable with conditions.

**Required output elements:**
- Classification: Suitable for pilot
- Evidence assessment showing strong support
- Privacy note about contract sensitivity
- Condition that data handling is confirmed
- At least one failure case evaluated

**Failure conditions:**
- Fails to classify as suitable despite strong evidence
- Ignores the privacy note about contracts
- Does not note that human review of every summary is a strength

**Pass criteria:**
Agent classifies as suitable, notes privacy implication, evaluates
at least one failure case, provides a conditional recommendation.

---

## Case 10: Unsuitable High-Risk Workflow

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
Classifies as unsuitable. Notes bias and legal risks.

**Required output elements:**
- Classification: Unsuitable for pilot
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
Agent classifies as unsuitable, identifies at least 3 critical
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
is at the boundary of "small pilot" limits. Evaluates the workflow
positively but flags the scope concern. Asks whether the 4th
project was added intentionally.

**Required output elements:**
- Identification that scope has changed (3 to 4 projects)
- Note that 4 projects may be at the boundary of pilot limits
- Otherwise positive assessment
- Question about whether the scope change is intentional

**Failure conditions:**
- Ignores the scope discrepancy
- Classifies as unsuitable solely because of 4 vs. 3 projects
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
- Classification as suitable with condition that fallback is defined

**Failure conditions:**
- Ignores the missing fallback
- Classifies as unsuitable solely because of missing fallback
- Does not ask about fallback procedure

**Pass criteria:**
Agent identifies the gap, asks about fallback, provides a
conditional recommendation that includes the fallback requirement.
