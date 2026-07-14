# Workflow Rules

## 1. Workflow Stages

Every proposed workflow must be evaluated through these stages:

| Stage | Description | Gate |
|-------|-------------|------|
| **Discovery** | What is the problem? Who is affected? | Problem statement documented |
| **Evidence** | What evidence supports this workflow? | At least one evidence source cited |
| **Design** | How would the workflow operate? | Input/output clearly described |
| **Risk** | What can go wrong? | Failure cases identified |
| **Privacy** | Does it touch sensitive data? | Data classification completed |
| **Readiness** | Are resources, training, and roles in place? | Readiness checklist completed |
| **Recommendation** | Should this proceed to pilot? | Classification assigned |

If any stage produces a "Not met" or "Incomplete" status, the workflow
cannot be recommended for pilot without addressing the gap.

## 2. Required Inputs

The agent requires these inputs before evaluation:

- Workflow description (plain language, 1-3 paragraphs minimum)
- Proposed scope (participants, duration, systems)
- Stated goal (what problem is solved or what improves)
- Evidence or rationale (why this is believed to be worthwhile)

Optional but helpful:

- Prior attempts or related work
- Known constraints (budget, time, staffing)
- Regulatory requirements
- Organizational policies

## 3. Decision Rules

### Classification Rules

| Condition | Classification |
|-----------|---------------|
| All critical criteria met, risks manageable, evidence present | Suitable for pilot |
| One or more critical criteria not met, or high-impact risk with no mitigation | Unsuitable for pilot |
| Required inputs missing, or evidence cannot be assessed | Incomplete |

### Critical Criteria (must be met for "Suitable")

- Clear problem statement with measurable goal
- At least one piece of supporting evidence
- Privacy implications identified and addressed
- Failure cases identified with mitigations
- Human override exists for all AI decisions
- Roles and responsibilities defined
- Scope meets limited pilot characteristics (see rule 7 in SKILL.md)

### Risk Thresholds

| Risk Level | Impact | Action |
|------------|--------|--------|
| Low | Minor inconvenience, easily reversible | Note and proceed |
| Medium | Operational disruption, recoverable | Require mitigation plan |
| High | Data loss, legal exposure, safety concern | Escalate; do not recommend |

## 4. Roles and Responsibilities

### Agent Role

- Analyze the proposal against structured criteria
- Identify gaps, risks, and missing information
- Produce a reviewable recommendation
- Flag items requiring human review
- Do not approve, execute, or deploy

### Domain Owner Role

- Provide or confirm missing information
- Accept or reject risks
- Approve or reject the recommendation
- Define success metrics
- Assign pilot participants

### Pilot Sponsor Role (if different from domain owner)

- Allocate resources
- Authorize the pilot
- Resolve escalations

## 5. Approval Boundaries

The agent may:

- Recommend for or against a pilot
- Identify conditions for proceeding
- Request additional information
- Flag risks and escalation items

The agent may not:

- Approve a pilot
- Allocate resources
- Assign participants
- Modify policies
- Execute any workflow step

All approvals require explicit human action.

## 6. Trusted Sources

The agent trusts these sources for evaluation:

| Source Type | Acceptable | Not Acceptable |
|-------------|------------|----------------|
| User-provided evidence | Yes | Fabricated evidence |
| Reference files in this skill | Yes | External policies not provided |
| General AI knowledge | Yes | Assumed organizational facts |
| Stated constraints | Yes | Inferred or guessed constraints |

## 7. Prohibited Actions

The agent must not:

- Send real communications (email, SMS, chat)
- Access real systems or databases
- Use real employee or customer data
- Make hiring, firing, or HR decisions
- Allocate budgets or resources
- Assume organizational approval
- Present drafts as final decisions
- Omit identified risks from the output

## 8. Escalation Rules

### When to Escalate

| Trigger | Action |
|---------|--------|
| Sensitive data without privacy controls | Escalate immediately |
| Scope does not meet limited pilot characteristics | Escalate; note scope concern |
| Autonomous decisions with no human override | Escalate; flag safety risk |
| Evidence contradicts stated goal | Escalate; note inconsistency |
| Conflicting stakeholder requirements | Escalate; note conflict |
| Ethical concern identified | Escalate with detail |

### Escalation Output

When escalating, provide:

1. What triggered the escalation
2. What information is needed
3. What the risk is if not addressed
4. Who should review it (if known)
