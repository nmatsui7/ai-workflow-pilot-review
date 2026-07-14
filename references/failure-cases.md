# Failure Cases

Each failure case describes a realistic scenario, why it may happen,
its impact, how to detect it, and the required mitigation.

---

## Failure Case 1: Hallucinated Output Treated as Fact

**Scenario:** The AI generates plausible-sounding but incorrect
information that users accept without verification.

**Why it may happen:** The AI model has knowledge gaps or the input
data is ambiguous. Users may trust AI output due to speed and
confidence of delivery.

**Possible impact:** Incorrect decisions based on false information;
reduced trust in the system; potential legal or compliance exposure.

**How the agent should detect it:** Check whether the workflow
includes verification steps for AI output. Check whether the
stated goal requires factual accuracy. Check whether output is
reviewed before use.

**Required mitigation:** Require human review of all AI-generated
output before it is used in decisions. Define what constitutes
"acceptable accuracy" for the workflow.

**Human escalation required:** Yes, if the workflow involves
financial, legal, health, or safety decisions.

---

## Failure Case 2: Privacy Breach via Indirect Data Exposure

**Scenario:** The AI workflow processes data that indirectly
identifies individuals, even though it does not directly collect
PII.

**Why it may happen:** The data contains quasi-identifiers
(combination of age, location, role, etc.) that can be used to
re-identify individuals. The workflow designer may not recognize
this risk.

**Possible impact:** Regulatory violation (GDPR, CCPA, HIPAA);
loss of employee or customer trust; legal liability.

**How the agent should detect it:** Check whether the workflow
involves any data that could identify individuals, even
indirectly. Check whether data anonymization or aggregation
is described.

**Required mitigation:** Require data classification before
proceeding. Require anonymization or aggregation where
possible. Require legal review if personal data is involved.

**Human escalation required:** Yes, always when personal data
is involved.

---

## Failure Case 3: Excessive Autonomy Without Override

**Scenario:** The AI workflow makes decisions or takes actions
without human review, and there is no mechanism to override or
correct it.

**Why it may happen:** The workflow is designed for efficiency
and the human review step is seen as a bottleneck. The designer
prioritizes speed over safety.

**Possible impact:** Incorrect actions taken at scale; inability
to correct errors; loss of human control; safety concerns.

**How the agent should detect it:** Check whether the workflow
includes human review checkpoints. Check whether there is an
override mechanism. Check whether the AI can take actions
autonomously.

**Required mitigation:** Require human override for all
consequential decisions. Define review checkpoints. Limit
AI autonomy to low-risk actions only.

**Human escalation required:** Yes, if the workflow involves
any autonomous decision-making.

---

## Failure Case 4: Role Confusion and Accountability Gap

**Scenario:** Multiple people are involved in the workflow but
no one is clearly responsible for oversight, exceptions, or
escalation.

**Why it may happen:** The workflow is introduced as a "team
effort" without assigning specific responsibilities. Roles
are assumed rather than documented.

**Possible impact:** Errors go undetected; escalations are not
handled; no one monitors the pilot; the pilot fails without
a clear cause being identified.

**How the agent should detect it:** Check whether roles and
responsibilities are explicitly defined. Check whether
oversight, exception handling, and escalation are assigned
to specific roles.

**Required mitigation:** Require explicit role assignments
before the pilot begins. Define who is responsible for
monitoring, exception handling, and escalation.

**Human escalation required:** Yes, if roles are not clearly
assigned.

---

## Failure Case 5: Training Gap Causes Adoption Failure

**Scenario:** The pilot is launched without adequate training,
and participants do not understand how to use the AI workflow
effectively.

**Why it may happen:** Training is assumed to be intuitive or
is deferred to "later." The workflow designer underestimates
the learning curve.

**Possible impact:** Low adoption; incorrect usage; frustration;
reduced productivity during the pilot; negative perception of
AI tools.

**How the agent should detect it:** Check whether training
materials and time are planned. Check whether the workflow
assumes user knowledge that may not exist. Check whether the
pilot timeline accounts for a learning period.

**Required mitigation:** Require a training plan with defined
content, delivery method, and timeline. Build learning period
into the pilot schedule.

**Human escalation required:** Yes, if no training plan exists.

---

## Failure Case 6: Evidence Contradicts Stated Goal

**Scenario:** The evidence provided supports a different
conclusion than the one the workflow claims to achieve.

**Why it may happen:** The proposal is based on optimism or
cherry-picked evidence. The designer may not have evaluated
the evidence critically.

**Possible impact:** The pilot wastes resources on a workflow
that does not achieve its stated goal; opportunity cost of
not pursuing better alternatives.

**How the agent should detect it:** Compare the stated goal
with the evidence. Check whether the evidence actually
supports the claimed outcome. Check whether the evidence is
from a relevant context.

**Required mitigation:** Flag the inconsistency. Request
additional evidence or a revised goal. Recommend against
proceeding until the inconsistency is resolved.

**Human escalation required:** Yes, if the evidence clearly
contradicts the goal.

---

## Failure Case 7: Scope Creep Beyond Pilot Limits

**Scenario:** The workflow is described as a limited pilot but
the scope includes multiple teams, systems, or a timeline that
exceeds what the team can reasonably manage and evaluate.

**Why it may happen:** The designer wants to maximize impact
or does not understand the purpose of limiting scope. The
proposal is vague about boundaries.

**Possible impact:** The pilot becomes a de facto production
deployment without adequate testing; resource strain; inability
to evaluate results fairly.

**How the agent should detect it:** Check whether the proposed
scope meets the limited pilot characteristics: bounded workflow
and user group, limited consequences, reversible outcomes, named
owner and reviewer, measurable baseline, manageable reviewer
workload, sufficient duration, and explicit stop/revise criteria.
Check whether the workflow touches multiple systems or departments.

**Required mitigation:** Recommend reducing the scope to
within pilot limits. Clarify what is in and out of scope
before proceeding.

**Human escalation required:** Yes, if scope exceeds pilot
limits.

---

## Failure Case 8: Unapproved Knowledge Sources

**Scenario:** The workflow relies on external data sources,
third-party APIs, or unapproved tools that introduce security
or compliance risks.

**Why it may happen:** The designer selects tools for
capability without considering security or compliance
implications. The workflow assumes access to systems that
have not been approved.

**Possible impact:** Security breach; compliance violation;
data leakage; dependency on unapproved third-party services.

**How the agent should detect it:** Check whether the workflow
references external sources, APIs, or tools not on the
approved list. Check whether data flows to external systems.

**Required mitigation:** Flag unapproved sources. Require
security and compliance review before using external sources.
Recommend approved alternatives if available.

**Human escalation required:** Yes, if unapproved external
sources are involved.

---

## Failure Case 9: No Fallback for AI Failure

**Scenario:** The AI system fails or produces poor output,
and the workflow has no procedure to continue without it.

**Why it may happen:** The workflow assumes the AI will always
work. No one planned for downtime, errors, or degraded
performance.

**Possible impact:** Workflow stops entirely; employees cannot
perform their tasks; customer service is disrupted; the pilot
is perceived as a failure.

**How the agent should detect it:** Check whether a fallback
procedure is described. Check whether the workflow can
function without AI assistance. Check whether degraded
operation is planned.

**Required mitigation:** Require a fallback procedure. Define
what happens when AI output is unavailable or unacceptable.
Ensure the workflow can operate manually during AI outages.

**Human escalation required:** Yes, if no fallback exists.

---

## Failure Case 10: Recognition and Incentive Misalignment

**Scenario:** Employees are asked to participate in the pilot
but there is no recognition, incentive, or accommodation for
the additional workload.

**Why it may happen:** The pilot is presented as a
"requirement" or "opportunity" without considering the
employee's perspective. The designer assumes goodwill is
sufficient.

**Possible impact:** Low engagement; resentment; selective
participation; unreliable evaluation data; negative
perception of AI initiatives.

**How the agent should detect it:** Check whether employee
incentives, recognition, or workload accommodations are
mentioned. Check whether participation is voluntary or
mandated.

**Required mitigation:** Recommend defining recognition,
incentives, or workload adjustments before the pilot.
Recommend voluntary participation where possible.

**Human escalation required:** No, but flag as a risk. The
domain owner should address it.
