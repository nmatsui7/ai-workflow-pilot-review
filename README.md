# AI-Workflow Pilot Review Skill

## Business Problem

Organizations considering AI-assisted workflows often lack a
structured way to evaluate whether a proposed workflow is suitable
for a limited pilot. Without a consistent review process, proposals
may be approved without adequate evidence, approved with hidden
risks, or rejected without proper analysis. This skill provides
a repeatable, transparent evaluation framework.

## What the Skill Does

This skill evaluates proposed AI-assisted workplace workflows and
produces a structured review covering:

- Completeness of the proposal
- Workflow decomposition and tool selection
- Quality of supporting evidence
- Privacy and data handling implications
- Foreseeable failure cases and adoption risks
- Human-review requirements
- Employee and customer impact
- Workload implications and reviewer burden
- Role clarity and accountability
- Staff trust, recognition, and incentives
- Output quality standards
- Knowledge maturity and lesson sharing
- Approval readiness

The skill classifies each proposal as:

- **Suitable for pilot** - meets critical criteria, risks are
  manageable, proceed with conditions
- **Unsuitable for pilot** - critical criteria not met, risks
  too high, do not recommend
- **Incomplete** - insufficient information to evaluate, request
  missing details

## What the Skill Does Not Do

- It does not approve or execute any workflow
- It does not deploy, configure, or activate AI tools
- It does not access real employee or customer data
- It does not make hiring, firing, or HR decisions
- It does not allocate budgets or resources
- It does not produce final decisions (all recommendations
  require human approval)

## Folder Structure

```
ai-workflow-pilot-review/
├── SKILL.md                         # Core skill instructions
├── references/
│   ├── workflow-rules.md            # Workflow stages, decision rules,
│   │                                # roles, approval boundaries
│   ├── review-checklist.md          # Detailed evaluation checklist
│   ├── failure-cases.md             # 10 documented failure cases
│   ├── pilot-selection-criteria.md  # Pilot readiness criteria
│   ├── adoption-risk-types.md       # 12 adoption risk types
│   ├── knowledge-review-guidance.md # Knowledge maturity stages
│   └── method-notes.md              # Informal supporting methodology
├── examples/
│   ├── suitable-example.md          # Example: AI ticket summarization
│   ├── unsuitable-example.md        # Example: AI status reports
│   └── incomplete-example.md        # Example: AI onboarding assistant
├── tests/
│   └── evaluation-cases.md          # 20 test cases for evaluation
└── README.md                        # This file
```

## How to Invoke or Test

### Invocation

Provide the skill to an AI agent that supports the SKILL.md pattern.
The agent will activate when it detects a request to evaluate an
AI-assisted workflow.

### Test Prompt

```
I want to use AI to help our marketing team write social media
posts. The AI would generate drafts based on our brand guidelines
and recent campaign data. The marketing manager would review
before posting. Scope: 4 people, 6 weeks, 3 social channels.
Goal: increase posting frequency by 30%. Evidence: we tried this
informally and it seemed helpful.
```

### Sample Prompts

**Complete proposal:**
```
Evaluate this workflow for pilot suitability:
We want to use AI to summarize customer support tickets. 8 agents,
6 weeks, Zendesk. Goal: reduce summary time by 30%. Evidence:
manual test with 50 tickets showed 84% quality rating.
```

**Vague proposal:**
```
We're thinking about using AI for something in our finance
department. Can you help us evaluate if it's a good idea?
```

**High-risk proposal:**
```
We want AI to automatically approve all customer refund requests
under $100. No human review. Goal: instant refunds.
```

## Safety and Governance Boundaries

1. **No real data.** The skill operates on user-provided
   descriptions, not real data. It must not request or access
   real employee, customer, or financial data.

2. **No external actions.** The skill does not send emails,
   access APIs, configure tools, or take any action outside
   of producing a review document.

3. **Human approval required.** All recommendations are drafts
   that require explicit human approval before any action is
   taken.

4. **Conservative defaults.** When information is missing, the
   skill defaults to "not met" or "incomplete" rather than
   assuming compliance.

5. **Transparent reasoning.** The skill labels assumptions,
   identifies gaps, and does not present uncertain conclusions
   as facts.

6. **Scope limited.** The skill evaluates limited pilot proposals.
   A limited pilot is defined by characteristics (bounded workflow,
   limited consequences, reversible outcomes, named owner and
   reviewer, measurable baseline, manageable reviewer workload,
   sufficient duration, explicit stop/revise criteria), not by
   fixed participant counts or duration.

## Limitations

- The skill cannot verify organizational policies it has not
  been given access to.
- The skill cannot assess technical feasibility in detail.
- The skill relies on the accuracy of user-provided information.
- The skill cannot predict real-world outcomes; it evaluates
  proposal quality and risk.
- The skill does not replace legal, compliance, or HR review.

## Supporting Methodology

The file `references/method-notes.md` contains informal
workflow-adoption guidance based on public learning materials.
These notes informed the review criteria in this skill, particularly
around:

- Workflow-first AI adoption (start from problems, not tools)
- Workflow decomposition (break work into steps before choosing tools)
- Knowledge sources and evidence
- Failure cases and human review
- Employee workload, trust, role clarity, and recognition
- Knowledge maturity and periodic review

These notes are not a legal policy, formal research standard, or
independently validated framework. They are informal learning
material used to shape the skill's evaluation criteria. The skill
remains advisory — domain owners must validate organization-specific
rules, regulatory requirements, and operational constraints.

### Source and Attribution

The method notes are based on public videos from 株式会社AX:
https://youtu.be/sY0gFHS-kL4?si=VeaS2DXC7HknSgVn

- The material was used as informal learning input for this project.
- The notes reflect the project author's interpretation of the
  source material, not a direct translation or reproduction.
- This project is independent and is not affiliated with or endorsed
  by 株式会社AX.
- This is not an official translation of the source material.

The full attribution and independence statement are preserved in
`references/method-notes.md`.

## How a Domain Owner Should Revise This Skill

### Adjust Scope Limits

The skill defines a limited pilot by characteristics (bounded
workflow, limited consequences, reversible outcomes, named owner
and reviewer, measurable baseline, manageable reviewer workload,
sufficient duration, explicit stop/revise criteria), not by fixed
numbers. Record participant counts and duration as part of your
proposal. Adjust the mandatory gates and advisory checks to match
your organization's risk tolerance.

### Add Regulatory Frameworks

If your organization is subject to specific regulations (GDPR,
HIPAA, SOC 2, etc.), add them to the workflow rules and review
checklist. The current skill flags privacy concerns generically.

### Customize Failure Cases

The 10 failure cases in `references/failure-cases.md` are
general. Replace or supplement them with failure cases specific
to your industry, technology stack, or organizational context.

### Define Evidence Standards

The skill flags missing evidence but does not define what
"good evidence" looks like for your organization. Add specific
requirements (e.g., internal testing with X samples, comparison
to baseline, independent validation).

### Add Approval Workflows

The skill produces recommendations but does not define the
approval chain. Add your organization's approval process,
decision-makers, and escalation paths.

### Integrate with Existing Tools

If your organization uses specific tools for project management,
risk assessment, or compliance, document how this skill
integrates with them.

## Why This Is a Business Workflow Artifact, Not Merely a Prompt

This skill is not a single prompt that produces an answer. It is
a structured business workflow artifact that:

1. **Defines a repeatable process.** The 9-step workflow ensures
   every proposal is evaluated consistently, regardless of who
   is doing the evaluation or what AI agent is being used.

2. **Encodes domain knowledge.** The reference files contain
   accumulated knowledge about what makes AI workflows succeed
   or fail, including 10 documented failure cases with detection
   methods and mitigations.

3. **Enforces governance.** The skill includes explicit rules
   about what the agent must not do, when it must escalate, and
   when human approval is required. These are governance
   controls, not prompt suggestions.

4. **Produces reviewable artifacts.** The output is a structured
   document that can be reviewed, challenged, and approved by
   humans. It is not a recommendation buried in a conversation.

5. **Is testable.** The 20 evaluation cases provide concrete
   scenarios with pass/fail criteria, making it possible to
   verify that the skill works correctly and consistently.

6. **Is maintainable.** The separation of core instructions
   (SKILL.md), detailed rules (references/), examples
   (examples/), and tests (tests/) makes it possible to update
   individual components without rewriting the entire skill.

This is the difference between a prompt and a business workflow
artifact: a prompt asks an AI to do something. A workflow
artifact defines how work should be done, what rules apply,
what outputs are expected, and how quality is verified.
