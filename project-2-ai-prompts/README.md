# Project 2 — AI PM Prompts

**Author:** Karun Mehta · AIGP · PMP
**Tagline:** Plan with evidence. Govern decisions. Deliver outcomes.

> **Portfolio and educational use.** These prompts are reusable starting points, not substitutes for professional judgment, organizational policy, legal review, financial approval, security review, or accountable human decision-making. Do not enter confidential, regulated, personal, or proprietary information into an AI tool unless the tool and use are explicitly authorized.

<img width="1122" height="1402" alt="image" src="https://github.com/user-attachments/assets/233d4e5d-1b0f-493b-9bdd-3abfdbc3ba16" />

---

## Executive Summary

This library turns common project and program management activities into structured, auditable AI-assisted workflows. It covers project intake, chartering, scope, estimation, milestones, dependencies, resources, Agile delivery, risk, change, quality, UAT, release readiness, executive reporting, recovery, and AI-specific governance.

The design deliberately separates three responsibilities:

- **AI drafts and analyzes.** It structures inputs, identifies gaps, calculates when reliable data is supplied, and proposes options.
- **The project manager validates.** The PM checks source records, challenges assumptions, resolves conflicts, and confirms owners and dates.
- **Authorized stakeholders decide.** Sponsors, product owners, risk partners, and governance bodies retain approvals and accountability.

## About the Output Snapshots

Every prompt includes an illustrative output snapshot immediately after the copy-paste prompt. The snapshots show the expected structure, level of specificity, and decision orientation before the prompt is used.

**All names, dates, values, thresholds, projects, findings, recommendations, and decisions in the snapshots are fictional examples.** They are not actual delivery evidence and must not be reused as organizational commitments. Replace them with validated information from approved source systems and obtain the required human review before use.

## What Makes This Library Different

Many prompt collections stop at generating polished text. This library treats AI output as a **governed project artifact**. Every core prompt is designed to produce:

- a decision-ready output rather than generic advice;
- explicit facts, assumptions, unknowns, and confidence limits;
- owners, due dates, dependencies, thresholds, and escalation paths;
- source traceability and a validation checklist;
- human approval before commitments, external communication, or system action.

## KM-PROMPT Method

| Element | Meaning | What to provide |
|---|---|---|
| K | Key objective | The decision, deliverable, or outcome required |
| M | Materials | Approved source records such as charter, backlog, RAID log, budget, plan, or meeting notes |
| P | Persona | The relevant role, such as program manager, Agile coach, risk lead, or QA leader |
| R | Requirements | Scope, constraints, methodology, policies, thresholds, dates, and audience |
| O | Output | Exact artifact, table, fields, format, and level of detail |
| M | Measures | Success criteria, KPIs, tolerances, and confidence expectations |
| P | Permissions | Actions the AI may recommend versus actions requiring human approval |
| T | Traceability | Sources, assumptions, decisions, versions, and evidence to retain |

## Standard Control Wrapper

Add this wrapper to any prompt when the output will support a material project decision.

```
Use only the information I provide and clearly identified general project-management methods.

Control requirements:
1. Do not invent project facts, dates, costs, capacity, status, approvals, or stakeholder commitments.
2. Separate verified facts, calculations, assumptions, inferences, recommendations, and unresolved questions.
3. Cite the supplied source record or field supporting each material conclusion.
4. Show formulas and calculation inputs for estimates, forecasts, scores, and prioritization.
5. Identify contradictory, missing, stale, or low-confidence information before recommending action.
6. Do not send messages, modify systems, assign resources, change scope, approve funding, accept risk, or make a release decision.
7. Mark every item that requires accountable human review or approval.
8. End with a validation checklist: source accuracy, owner confirmation, date confirmation, dependency check, risk review, and required approvals.
```

## Standardized Prompt Format

Every prompt follows the same validated structure:

```
# [Prompt Name]

## Metadata
- **ID**: `category-prompt-slug`
- **Version**: 1.0.0
- **Category**: Primary category
- **Tags**: searchable, keywords, here
- **Complexity**: simple | intermediate | advanced
- **Interaction**: single-shot | conversational | iterative
- **Models**: Claude 6+, GPT-5+

## Overview
2-3 sentences explaining what the prompt does and who it's for.

## When to Use
- Specific scenario 1
- Specific scenario 2

**Don't use for**: Anti-patterns where this prompt isn't appropriate

---

## Prompt

<role>Expert identity with specific credentials and experience</role>

<context>Situation, success criteria, and key assumptions</context>

<input_handling>
Required: Must-have inputs
Optional: Inferred defaults when not provided
</input_handling>

<task>
Clear steps (3-7) for what to accomplish
</task>

<output_specification>
Format, length, and structure requirements
</output_specification>

<quality_criteria>
Measurable standards for excellent output
</quality_criteria>

<constraints>
Hard boundaries and limitations
</constraints>

---

## Example Usage

### Input
Realistic user request (20-200 words)

### Output
Representative response demonstrating quality (100-600 words)

## Related Prompts
Links to complementary prompts
```

### XML Tag Structure

The prompt section uses semantic XML tags for consistent parsing:

| Tag | Purpose | Content |
|---|---|---|
| `<role>` | Expert identity | Specific credentials, experience, reasoning approach |
| `<context>` | Situation framing | When used, success criteria, key assumptions |
| `<input_handling>` | Input specification | Required vs optional inputs with defaults |
| `<task>` | Process steps | 3-7 numbered action steps |
| `<output_specification>` | Deliverable format | Format, length, structure, must-include elements |
| `<quality_criteria>` | Success measures | Objective standards and anti-patterns |
| `<constraints>` | Hard boundaries | Non-negotiable limits on scope/format |

### Quality Gates

Every prompt passes these 11 validation checks:

| Gate | Requirement |
|---|---|
| `metadata_complete` | All required fields present (ID, Version, Category, Tags, Complexity, Interaction, Models) |
| `overview_concise` | 3 sentences or fewer, no marketing fluff |
| `role_specific` | Concrete expertise defined, not "I'll help you" |
| `inputs_categorized` | Required vs optional distinguished with defaults |
| `task_structured` | 3-7 clear numbered steps |
| `outputs_specified` | Format + length + requirements for each deliverable |
| `criteria_measurable` | Objective quality standards, not vague aspirations |
| `example_realistic` | Input shows real usage (20-200 words) |
| `example_concise` | Output demonstrates pattern (100-600 words) |
| `no_duplication` | No repeated information across sections |
| `copy_paste_ready` | Prompt section is standalone and clearly delimited |

## Prompt Catalog

| ID | Prompt | Lifecycle Area | Primary Output |
|---|---|---|---|
| PM-01 | Project Intake and Prioritization | Intake | Scored intake recommendation |
| PM-02 | Project Charter Builder | Initiation | Draft charter |
| PM-03 | Stakeholder Map and RACI | Initiation | Stakeholder matrix and RACI |
| PM-04 | Scope and Requirements Baseline | Planning | Scope and requirements baseline |
| PM-05 | WBS, Milestones, and Critical Path | Planning | Delivery plan |
| PM-06 | Dependency Management | Planning | Dependency register |
| PM-07 | Three-Point Estimation | Estimation | PERT estimate and range |
| PM-08 | Resource and Capacity Plan | Planning | Capacity and allocation plan |
| PM-09 | Budget and EVM Baseline | Planning | Cost baseline and EVM model |
| PM-10 | RAID Register | Governance | RAID log |
| PM-11 | User Stories and Acceptance Criteria | Agile | Ready backlog items |
| PM-12 | Sprint Planning | Agile | Sprint plan and goal |
| PM-13 | PI Planning and Cross-Team Alignment | Agile at Scale | PI objectives and dependency plan |
| PM-14 | Daily Delivery and Impediment Review | Execution | Actionable delivery brief |
| PM-15 | Weekly Executive Status | Reporting | Executive status report |
| PM-16 | Forecast and Variance Analysis | Control | EAC, ETC, schedule forecast |
| PM-17 | Change Request and Scope Creep | Change Control | Impact assessment and decision pack |
| PM-18 | Decision Memo | Governance | Options and recommendation |
| PM-19 | Vendor and External Dependency Review | Procurement | Vendor action and escalation plan |
| PM-20 | Quality and UAT Readiness | Quality | Entry/exit readiness assessment |
| PM-21 | Release Go/No-Go | Release | Evidence-based release recommendation |
| PM-22 | Project Recovery Plan | Recovery | Stabilization and recovery plan |
| PM-23 | Postmortem and Lessons Learned | Closure | Blameless postmortem |
| PM-24 | Roadmap Prioritization | Portfolio | Prioritized roadmap |
| PM-24B | Quarterly Program Roadmap Visualization | Portfolio | Timeline roadmap, data table, Gantt chart, validation report |
| PM-25 | Meeting-to-Action Converter | Execution | Decisions and action register |
| AI-PM-01 | AI Use-Case Intake and Risk Triage | AI Governance | AI intake recommendation |
| AI-PM-02 | GenAI/RAG Delivery Readiness | AI Delivery | Evaluation and release plan |
| AI-PM-03 | Agentic AI Deployment Readiness | Agent Governance | Autonomy and control assessment |
| AI-PM-04 | AI-Assisted PM Output Validation | AI Assurance | Validation record |
| AI-PM-05 | Prompt Evaluation and Change Control | Prompt Governance | Prompt test and approval record |

### 1. Intake and Initiation

<details>
<summary><strong>PM-01 · Project Intake and Prioritization</strong></summary>

**Use when:** A new initiative needs an evidence-based intake decision.

```
Act as an enterprise portfolio manager. Evaluate the proposed initiative below without assuming approval.

Inputs:
- Business problem: [PROBLEM]
- Proposed outcome: [OUTCOME]
- Sponsor and stakeholders: [NAMES/ROLES]
- Strategic objective: [OBJECTIVE]
- Expected benefits: [BENEFITS]
- Cost and capacity estimate: [ESTIMATE]
- Target date and constraints: [DATE/CONSTRAINTS]
- Known risks, dependencies, and regulatory impact: [DETAILS]
- Candidate scoring model and weights: [MODEL]

Tasks:
1. Test whether the problem, outcome, scope, sponsor, value, funding, and measurable success criteria are sufficiently defined.
2. Score strategic alignment, customer/business value, urgency, effort, dependency complexity, delivery risk, compliance impact, and readiness. Show weights, evidence, formula, and sensitivity.
3. Identify duplicate or overlapping initiatives and information still required.
4. Recommend one disposition: advance to discovery, hold for evidence, combine, defer, or decline.

Output:
- One-paragraph recommendation
- Scoring table
- Evidence gaps and assumptions
- Conditions to advance
- Named decision owner and required governance forum
```

**Illustrative output snapshot:**
> Recommendation: advance to discovery — problem and sponsor are clearly defined, but funding and success metrics need refinement before full approval.
>
> | Criterion | Weight | Score (1–5) | Weighted |
> |---|---|---|---|
> | Strategic alignment | 25% | 4 | 1.00 |
> | Business value | 20% | 3 | 0.60 |
> | Delivery risk | 15% | 2 | 0.30 |
>
> Total: 3.2/5 — conditional advance, pending funding confirmation from Finance.
</details>

<details>
<summary><strong>PM-02 · Project Charter Builder</strong></summary>

```
Act as a senior program manager. Draft a project charter from the approved inputs below.

Inputs: [BUSINESS CASE, OBJECTIVES, SCOPE, SPONSOR, STAKEHOLDERS, TARGET DATES, BUDGET, CONSTRAINTS, RISKS]

Create:
1. Executive summary and business problem
2. SMART objectives and measurable outcomes
3. In-scope and out-of-scope boundaries
4. Major deliverables and acceptance measures
5. High-level milestones and dependencies
6. Governance model, sponsor, PM authority, decision rights, and escalation path
7. Initial risks, assumptions, issues, and constraints
8. Budget and resource envelope, clearly marking unapproved estimates
9. Success metrics, reporting cadence, and closure criteria
10. Approval table with role, decision, date, and evidence link

Flag missing or contradictory information. Do not convert targets into commitments or list anyone as an approver unless the source record explicitly authorizes that role.
```

**Illustrative output snapshot:**
> Executive summary drafted (1 paragraph). SMART objectives: 3 defined, 1 flagged as not measurable ("improve customer experience" — needs a metric). Governance model: Sponsor = VP Operations, PM authority = Tier 2. Approval table lists 4 roles; 1 marked "Pending signature."
</details>

<details>
<summary><strong>PM-03 · Stakeholder Map and RACI</strong></summary>

```
Act as a program governance lead. Build a stakeholder engagement plan and RACI for [PROJECT/PROGRAM].

Inputs:
- Stakeholders and roles: [LIST]
- Workstreams and deliverables: [LIST]
- Known decision rights: [DETAILS]
- Governance forums and cadence: [DETAILS]
- Organizational constraints or conflicts: [DETAILS]

Analyze each stakeholder's influence, impact, interest, expectations, decision authority, information needs, and engagement risk. Create:
- stakeholder influence/interest matrix;
- engagement strategy and communication cadence;
- deliverable-level RACI with exactly one Accountable role per row;
- unresolved ownership conflicts;
- escalation path for overdue or disputed decisions;
- validation questions for the sponsor.

Do not infer authority from job title alone. Mark every unconfirmed assignment as Proposed until the accountable leader validates it.
```

**Illustrative output snapshot:**
> | Deliverable | R | A | C | I |
> |---|---|---|---|---|
> | Data migration plan | Data lead | Program sponsor | Security, Legal | All workstream leads |
>
> Flag: two stakeholders both marked "Accountable" on the vendor onboarding row — needs sponsor resolution before the RACI can be finalized.
</details>

### 2. Planning, Estimation, and Controls

<details>
<summary><strong>PM-04 · Scope and Requirements Baseline</strong></summary>

```
Act as a technical program manager and business analyst. Convert the supplied business needs into a controlled scope and requirements baseline.

Inputs: [BUSINESS NEEDS, WORKSHOP NOTES, PROCESS MAPS, ARCHITECTURE, POLICIES, CONSTRAINTS]

Produce:
1. Problem statement, target outcomes, and measurable success criteria
2. In scope, out of scope, assumptions, constraints, and exclusions
3. Functional and non-functional requirements with unique IDs
4. User, operational, data, integration, security, accessibility, privacy, compliance, performance, resilience, and support requirements
5. Acceptance criteria and proposed evidence source for each requirement
6. Requirements traceability matrix linking objective → requirement → deliverable → test/evidence → owner
7. Ambiguities, conflicts, gaps, and decisions needed
8. Baseline approval and change-control process

Preserve the language of approved requirements where precision matters. Do not silently resolve contradictions; surface them for decision.
```

**Illustrative output snapshot:**
> 12 functional requirements, 5 non-functional, each with a unique ID and traceability link. 2 requirements flagged as contradictory — the data retention window conflicts with a compliance requirement — surfaced as an open decision, not resolved silently.
</details>

<details>
<summary><strong>PM-05 · WBS, Milestones, and Critical Path</strong></summary>

```
Act as a project planning lead. Build a milestone-based delivery plan from the approved scope.

Inputs:
- Deliverables and acceptance criteria: [LIST]
- Target dates and fixed events: [DATES]
- Activities or backlog: [LIST]
- Dependencies and lead times: [DETAILS]
- Resource constraints and calendars: [DETAILS]
- Estimate confidence: [DETAILS]

Tasks:
1. Decompose deliverables into a WBS at a level that can be owned and measured.
2. Define milestones as zero-duration decision or acceptance points with completion evidence.
3. Sequence activities using finish-to-start, start-to-start, finish-to-finish, or start-to-finish dependencies.
4. Identify external dependencies, critical-path candidates, float, bottlenecks, and schedule assumptions.
5. Propose a baseline and two schedule scenarios: target and risk-adjusted.

Output a table with WBS ID, activity, deliverable, owner, duration, predecessor, dependency type, start, finish, milestone, acceptance evidence, float, and confidence. Flag dates that cannot be supported by the supplied estimates.
```

**Illustrative output snapshot:**
> | WBS ID | Activity | Owner | Start | Finish | Float |
> |---|---|---|---|---|---|
> | 1.2 | Data pipeline build | Data eng | Mar 3 | Mar 21 | 0 days (critical) |
>
> Two downstream milestones flagged as unsupported by the current estimate confidence — recommend revisiting before baselining.
</details>

<details>
<summary><strong>PM-06 · Dependency Management</strong></summary>

```
Act as a cross-program dependency manager. Create and analyze a dependency register.

Inputs: [WORKSTREAM PLANS, MILESTONES, INTERFACES, VENDOR DATES, ENVIRONMENT DATES, DATA NEEDS, DECISIONS]

For every dependency, capture: ID, requesting team, providing team, required deliverable, need-by date, committed date, status, predecessor, downstream impact, critical-path flag, owner, acceptance evidence, trigger, mitigation, contingency, and escalation date.

Then:
- find date conflicts, circular dependencies, unowned handoffs, and single points of failure;
- distinguish internal, external, technical, business, regulatory, data, environment, and vendor dependencies;
- rank by schedule exposure and blast radius;
- recommend the next action and governance forum;
- prepare a concise dependency heatmap and a seven-day action list.

Treat proposed dates as unconfirmed unless evidence shows a commitment by the accountable provider.
```

**Illustrative output snapshot:**
> 7 dependencies logged. 1 circular dependency detected — Team A needs Team B's API, Team B needs Team A's schema first. Top risk: vendor environment access, need-by date still unconfirmed by the vendor.
</details>

<details>
<summary><strong>PM-07 · Three-Point Estimation</strong></summary>

```
Act as an estimation facilitator. Estimate the work using expert inputs, decomposition, and three-point estimation. Do not create estimates without team evidence.

For each work item use:
- O = optimistic estimate
- M = most likely estimate
- P = pessimistic estimate
- PERT expected estimate = (O + 4M + P) / 6
- Standard deviation = (P - O) / 6

Inputs: [WORK ITEMS, O/M/P VALUES, TEAM ASSUMPTIONS, HISTORICAL ANALOGS, RISKS, DEPENDENCIES]

Produce a table showing O, M, P, expected estimate, standard deviation, confidence, estimator, basis of estimate, exclusions, risks, and contingency rationale. Aggregate only compatible units. Explain uncertainty drivers and run sensitivity analysis for the top three variables. Clearly distinguish effort, duration, elapsed time, and story points. End with questions the delivery team must answer before accepting the estimate.
```

**Illustrative output snapshot:**
> | Item | O | M | P | PERT | Std Dev |
> |---|---|---|---|---|---|
> | API integration | 5d | 8d | 15d | 8.7d | 1.7d |
>
> Sensitivity: vendor API documentation quality is the single biggest uncertainty driver — recommend a documentation spike before committing the estimate.
</details>

<details>
<summary><strong>PM-08 · Resource and Capacity Plan</strong></summary>

```
Act as a resource planning lead. Build a capacity plan without treating people as interchangeable units.

Inputs:
- Work and effort by skill: [DETAILS]
- Team members/roles and availability: [DETAILS]
- Sprint or calendar period: [DATES]
- Holidays, operational load, leave, and focus factor: [DETAILS]
- Required skills, location, vendor, and access constraints: [DETAILS]

Calculate gross capacity, deductions, net capacity, demand, utilization, and gap by role and period. Map skills to work, identify bottlenecks, key-person risk, over-allocation, onboarding lead time, and segregation-of-duties conflicts. Provide base, constrained, and recovery scenarios.

Output:
- capacity-versus-demand table;
- allocation proposal with assumptions;
- resource conflicts and delivery impact;
- options with cost, schedule, and risk tradeoffs;
- approvals needed before reallocating people or funding.

Do not recommend named-person assignments as final unless the responsible manager confirms availability.
```

**Illustrative output snapshot:**
> Net capacity: 340 hrs/sprint. Demand: 410 hrs. Gap: −70 hrs (over-allocated). Bottleneck: only one engineer is certified on the legacy system — flagged as key-person risk requiring a mitigation plan.
</details>

<details>
<summary><strong>PM-09 · Budget and EVM Baseline</strong></summary>

```
Act as a project controls analyst. Create a budget baseline and earned value model using the supplied approved figures.

Inputs: [WBS, TIME-PHASED BUDGET, ACTUAL COST, PERCENT COMPLETE METHOD, REPORTING DATE, CHANGE LOG]

Calculate and show formulas for PV, EV, AC, SV, CV, SPI, CPI, BAC, ETC, EAC, and VAC. State which EAC formula is appropriate and why. Reconcile approved changes to the current baseline and keep unapproved requests separate.

Output:
1. Executive interpretation in plain language
2. Metric table with source, formula, value, threshold, and status
3. Work-package variances and root-cause hypotheses
4. Forecast range and key sensitivities
5. Corrective-action options with owner and due date
6. Data-quality and approval gaps

Do not claim precision beyond the quality of progress and cost data. Flag division-by-zero, inconsistent cut-off dates, and subjective percent-complete inputs.
```

**Illustrative output snapshot:**
> SPI: 0.87 (behind schedule). CPI: 0.94 (slightly over budget). EAC (CPI-adjusted): $1.42M vs. BAC $1.30M. Data-quality flag: two work packages report inconsistent percent-complete methods, reducing forecast confidence.
</details>

<details>
<summary><strong>PM-10 · RAID Register</strong></summary>

```
Act as a program risk and controls lead. Convert the supplied artifacts into a clean RAID register.

Inputs: [STATUS REPORTS, PLANS, MEETING NOTES, DEFECTS, DECISIONS, ASSUMPTIONS, DEPENDENCIES]

Classify each item correctly as Risk, Assumption, Issue, or Dependency. Remove duplicates while preserving source links. For risks, score probability and impact on a 1–5 scale, calculate inherent and residual exposure, and define trigger, response strategy, mitigation, contingency, owner, due date, and review cadence. For issues, include current impact, containment, resolution plan, escalation level, and target closure. For assumptions, define a validation owner and date. For dependencies, identify provider, consumer, need-by date, and acceptance evidence.

Output the updated RAID table, top exposures, overdue actions, trend, decisions required, and proposed escalations. Never mark an item closed without closure evidence and owner confirmation.
```

**Illustrative output snapshot:**
> 14 items classified: 6 Risks, 3 Assumptions, 3 Issues, 2 Dependencies. Top exposure: vendor SLA risk, residual score 12/25 (High). Two items marked "closed" in the source notes were reopened pending actual closure evidence.
</details>

### 3. Agile and Scaled Delivery

<details>
<summary><strong>PM-11 · User Stories and Acceptance Criteria</strong></summary>

```
Act as a product owner and delivery analyst. Convert the approved requirement into INVEST-aligned user stories.

Input requirement: [REQUIREMENT]
Users and journey: [DETAILS]
Business rules and constraints: [DETAILS]
Non-functional needs: [DETAILS]

For each story provide:
- story ID and title;
- As a / I want / So that statement;
- business value and priority;
- preconditions, dependencies, assumptions, and exclusions;
- Given/When/Then acceptance criteria including happy path, edge cases, errors, access, data, performance, accessibility, security, auditability, and recovery where relevant;
- test-data and environment needs;
- Definition of Ready gaps;
- traceability to the source requirement.

Split stories that are too large and explain the split. Do not add business rules not present in the source; list them as questions.
```

**Illustrative output snapshot:**
> Story: "As a claims adjuster, I want auto-populated fields from prior claims so that I reduce manual entry." 6 acceptance criteria including one edge case (duplicate claim ID) and one accessibility criterion. Split recommended — the original story exceeded a single sprint's worth of effort.
</details>

<details>
<summary><strong>PM-12 · Sprint Planning</strong></summary>

```
Act as an Agile planning facilitator. Create a feasible sprint proposal using the backlog and verified team capacity.

Inputs:
- Sprint dates and objective: [DETAILS]
- Prioritized backlog with estimates: [ITEMS]
- Definition of Ready and Definition of Done: [CRITERIA]
- Historical velocity range: [RANGE]
- Net capacity, skills, leave, and operational load: [DETAILS]
- Dependencies, carryover, defects, and risks: [DETAILS]

Tasks:
1. Validate readiness and identify items that should not enter the sprint.
2. Propose one outcome-focused sprint goal.
3. Select work within the lower of capacity-based and evidence-based velocity limits.
4. Sequence dependencies and balance feature, defect, technical-debt, and enablement work.
5. Identify stretch work separately and define a mid-sprint change rule.

Output committed proposal, stretch items, capacity math, goal-to-story traceability, dependencies, risks, owner confirmations, and planning questions. The team, not the AI, makes the final commitment.
```

**Illustrative output snapshot:**
> Sprint goal: "Ship the automated data-validation step end-to-end." Committed: 32 points (within the 28–36 velocity range). Stretch: 8 points. One dependency flagged as blocking until Tuesday.
</details>

<details>
<summary><strong>PM-13 · PI Planning and Cross-Team Alignment</strong></summary>

```
Act as a Release Train Engineer and technical program manager. Prepare a PI planning decision pack across [NUMBER] teams/workstreams.

Inputs: [BUSINESS PRIORITIES, TEAM CAPACITY, FEATURES, ARCHITECTURAL ENABLERS, MILESTONES, DEPENDENCIES, RISKS]

Create:
- draft business context and prioritized outcomes;
- team-by-team capacity and demand view;
- feature-to-team and objective-to-feature mapping;
- dependency board with provider, consumer, need-by iteration, and commitment status;
- proposed PI objectives with business value and measurable result;
- program risks classified as Resolved, Owned, Accepted, or Mitigated;
- confidence-vote questions and conditions requiring replanning;
- management-review decisions and escalation owners.

Identify sequencing conflicts, integration bottlenecks, environment/data constraints, and objectives that lack measurable value. Keep preliminary plans clearly marked until teams and business owners validate them.
```

**Illustrative output snapshot:**
> 5 teams, 3 cross-team dependencies flagged as uncommitted. 2 PI objectives lack a measurable result and were returned for rework. Confidence vote scheduled pending dependency resolution.
</details>

<details>
<summary><strong>PM-14 · Daily Delivery and Impediment Review</strong></summary>

```
Act as a delivery lead. Convert the latest team updates into an action-focused daily brief.

Inputs: [YESTERDAY/TODAY/BLOCKERS, BOARD STATUS, BUILD RESULTS, DEFECTS, DEPENDENCIES, DECISIONS]

Identify:
- progress toward the sprint or milestone goal;
- blocked work and blocker age;
- items with no movement or unclear ownership;
- cross-team dependencies due within five business days;
- scope added after commitment;
- defects or failed controls threatening completion;
- decisions required today.

Output a concise table with item, evidence, impact, owner, next action, due time/date, escalation threshold, and status. Follow it with the top three delivery risks and a proposed agenda for targeted follow-ups. Do not use individual activity counts as a performance judgment and do not turn the stand-up into a status report to management.
```

**Illustrative output snapshot:**
> | Item | Blocker age | Owner | Next action | Due |
> |---|---|---|---|---|
> | Environment access | 3 days | Infra lead | Escalate to manager | Today 3pm |
>
> Top 3 risks: environment access, one Sev-2 defect, and one dependency due in 2 days.
</details>

### 4. Execution, Reporting, and Decisions

<details>
<summary><strong>PM-15 · Weekly Executive Status</strong></summary>

```
Act as a senior program manager preparing a one-page executive status for [AUDIENCE].

Inputs: [APPROVED BASELINE, CURRENT STATUS, MILESTONES, BUDGET, RAID, QUALITY, DECISIONS, PRIOR REPORT]

Produce:
1. Overall Red/Amber/Green status with threshold-based rationale
2. Outcomes delivered this period
3. Milestone plan versus actual and forecast
4. Scope, schedule, budget, quality, resource, and dependency health
5. Top three risks/issues with exposure, owner, mitigation, and trend
6. Decisions or support required, including decision-by date and impact of delay
7. Next-period priorities
8. Changes since the prior report

Use concise executive language. Do not average away a critical workstream. Distinguish current facts from forecast. If the overall status conflicts with component status, explain why. Include source cut-off time and confidence/data-quality note.
```

**Illustrative output snapshot:**
> Overall: Amber (schedule slipping, budget on track). One decision needed by Friday: a scope trade-off on the reporting module. Data confidence: high (cutoff yesterday 5pm).
</details>

<details>
<summary><strong>PM-16 · Forecast and Variance Analysis</strong></summary>

```
Act as a project forecasting lead. Analyze current performance and produce a defensible completion forecast.

Inputs: [BASELINE, ACTUALS, REMAINING WORK, VELOCITY/THROUGHPUT, EVM DATA, RISKS, CHANGE LOG]

Compare baseline, current plan, actual performance, and forecast. Quantify schedule and cost variance, identify drivers, and separate one-time events from structural trends. Generate optimistic, most-likely, and pessimistic completion scenarios. If sufficient data exists, use EVM, throughput ranges, or Monte Carlo assumptions and show the selected method.

Output:
- forecast dates and cost range with confidence;
- milestone-level variance table;
- top sensitivity drivers;
- assumptions and excluded impacts;
- corrective actions with estimated benefit, cost, risk, and owner;
- thresholds that would trigger reforecast or escalation.

Do not present a single deterministic date when uncertainty is material.
```

**Illustrative output snapshot:**
> Most-likely completion: June 14 (range: June 8–June 24). Driver: velocity dropped 15% after two team members rotated off. Recommend reforecast if next sprint's velocity doesn't recover.
</details>

<details>
<summary><strong>PM-17 · Change Request and Scope Creep</strong></summary>

```
Act as a change-control lead. Assess the proposed change against the approved baseline.

Inputs:
- Change request and rationale: [DETAILS]
- Current scope, schedule, budget, architecture, controls, and commitments: [BASELINE]
- Requested effective date: [DATE]
- Dependencies and affected stakeholders: [DETAILS]

Determine whether this is a clarification, defect, regulatory requirement, dependency change, or scope change. Analyze impact to benefits, requirements, milestones, critical path, capacity, cost, quality, security, privacy, compliance, operations, vendors, and other programs. Identify work already started without approval.

Provide options: approve, reject, defer, split into MVP/later phase, or swap equal-priority scope. For each option show tradeoffs and residual risks. Produce a change-control record with recommendation, decision owner, decision-by date, implementation conditions, baseline updates, communications, and evidence required. Do not treat silence or meeting discussion as approval.
```

**Illustrative output snapshot:**
> Classification: scope change (not a clarification). Impact: +3 weeks to critical path, +$40K. Recommendation: defer to phase 2 — pending sponsor decision by Wednesday.
</details>

<details>
<summary><strong>PM-18 · Decision Memo</strong></summary>

```
Act as a program decision analyst. Prepare a concise, neutral decision memo.

Decision required: [QUESTION]
Decision owner and deadline: [ROLE/DATE]
Context and evidence: [DETAILS]
Constraints and non-negotiables: [DETAILS]
Options already considered: [OPTIONS]

Create:
- decision statement;
- why the decision is needed now;
- facts, assumptions, unknowns, and conflicts;
- 2–4 viable options, including status quo where appropriate;
- weighted comparison using agreed criteria;
- recommendation and rationale;
- consequences, reversibility, implementation steps, and residual risks;
- stakeholders consulted and dissenting views;
- approval/signature section and decision-log entry.

Show how the recommendation changes if the top assumption is wrong. The memo supports the decision owner; it does not make the decision.
```

**Illustrative output snapshot:**
> Decision: RAG vs. fine-tune for the support bot. Recommendation: RAG — reversible, faster to iterate, no retraining cost. If the assumption "data changes weekly" is wrong, fine-tune becomes more attractive due to lower long-term latency.
</details>

<details>
<summary><strong>PM-19 · Vendor and External Dependency Review</strong></summary>

```
Act as a vendor delivery manager. Review vendor performance and external dependencies using the contract, statement of work, plan, service levels, acceptance records, and issue log supplied.

Identify committed versus forecast dates, acceptance criteria, unresolved assumptions, access or environment needs, SLA trends, deliverable quality, invoice/milestone linkage, change requests, risks, and customer obligations. Separate contractual commitments from working-team expectations.

Output:
- deliverable and obligation tracker;
- plan-versus-actual performance;
- evidence gaps and disputed items;
- corrective actions and owners;
- escalation options consistent with the contract;
- upcoming decisions and acceptance dates;
- a factual draft agenda for the vendor review.

Do not provide legal conclusions. Flag clauses requiring procurement or legal interpretation, and require authorized approval before sending notices, accepting deliverables, changing access, or committing funds.
```

**Illustrative output snapshot:**
> 2 of 5 deliverables behind committed date. SLA trend: declining (3 late deliveries in 60 days). Recommend escalation per contract clause 4.2 — flagged for procurement review, not yet sent.
</details>

<details>
<summary><strong>PM-25 · Meeting-to-Action Converter</strong></summary>

```
Act as a program operations analyst. Convert the supplied transcript or notes into a governed meeting record.

Inputs: [TRANSCRIPT/NOTES, AGENDA, PARTICIPANTS, PRIOR ACTIONS]

Produce:
1. Purpose and concise discussion summary
2. Confirmed decisions, each with decision owner, date, rationale, and affected baseline
3. Actions with one owner, due date, dependency, and completion evidence
4. Risks, issues, assumptions, and dependencies to add or update
5. Open questions and parking-lot items
6. Conflicts or ambiguous statements requiring confirmation
7. Changes proposed but not approved

Do not infer agreement from discussion. Quote only short phrases when required to resolve ambiguity. Mark owner or due date as Unconfirmed when not explicit. End with a validation request the meeting chair can use before publishing the minutes.
```

**Illustrative output snapshot:**
> 3 confirmed decisions, 5 actions (all with a named owner and due date except one, marked Unconfirmed). One statement flagged as ambiguous — "we might revisit the timeline" — not treated as a decision.
</details>

### 5. Quality, Release, Recovery, and Closure

<details>
<summary><strong>PM-20 · Quality and UAT Readiness</strong></summary>

```
Act as an enterprise UAT program lead. Assess readiness across all workstreams using approved entry and exit criteria.

Inputs: [SCOPE/RTM, TEST PLAN, EXECUTION RESULTS, DEFECTS, ENVIRONMENT, DATA, ACCESS, TRAINING, DEPENDENCIES, SIGN-OFFS]

Assess:
- requirements and end-to-end scenario coverage;
- business-process, UI, API, data, integration, batch, and vendor-feed readiness;
- environment parity, stable code drop, test data, access, and training;
- P0/P1 execution and pass rate;
- Sev-1/Sev-2 status, aging, retest, leakage, and workaround risk;
- automation regression and non-functional evidence;
- cross-workstream golden paths and unresolved dependencies;
- business owner, product owner, technology, operations, and risk sign-offs.

Output a workstream heatmap, criterion-by-criterion evidence table, blockers, conditional-entry items, decision owners, and recommendation: Ready, Ready with Conditions, or Not Ready. Do not infer readiness from percentage complete alone or close a criterion without evidence.
```

**Illustrative output snapshot:**
> Recommendation: Ready with Conditions. 2 Sev-2 defects open with documented workarounds. 1 workstream (reporting) missing business owner sign-off — the blocking condition.
</details>

<details>
<summary><strong>PM-21 · Release Go/No-Go</strong></summary>

```
Act as a release governance lead. Prepare a release decision pack for [RELEASE].

Inputs: [SCOPE, TEST RESULTS, DEFECTS, SECURITY/COMPLIANCE RESULTS, CHANGE RECORDS, CUTOVER, ROLLBACK, SUPPORT, MONITORING, SIGN-OFFS]

Evaluate each release gate: scope traceability, code/build evidence, functional and regression results, performance, security, privacy, accessibility, data migration/reconciliation, operational readiness, training, communications, cutover rehearsal, rollback, monitoring, incident response, vendor readiness, and approvals.

For every failed or conditional gate, show impact, compensating control, expiration, risk owner, and exception approval. Provide a recommendation of Go, Conditional Go, or No-Go with evidence and residual risk. Include the cutover decision timeline, command structure, stop criteria, rollback triggers, and post-release validation plan.

The authorized release authority makes the final decision. Never convert an unresolved critical defect or missing mandatory approval into a conditional pass without documented exception authority.
```

**Illustrative output snapshot:**
> Recommendation: Conditional Go. Security gate passed. Rollback rehearsal not yet completed — compensating control: manual rollback runbook approved by the ops lead, expires in 48 hours.
</details>

<details>
<summary><strong>PM-22 · Project Recovery Plan</strong></summary>

```
Act as a project recovery specialist. Build an executable recovery plan for a program that is materially off track.

Inputs: [BASELINE, CURRENT PLAN, STATUS, RAID, BUDGET, QUALITY, RESOURCES, DECISIONS, STAKEHOLDER FEEDBACK]

First diagnose the failure pattern across scope, planning, dependencies, capacity, technology, quality, governance, decision latency, vendor performance, and organizational change. Separate symptoms from verified root causes.

Create a three-horizon plan:
- 0–72 hours: stabilize, establish facts, stop further exposure, assign command roles;
- 2 weeks: rebaseline critical work, close ownership gaps, restore delivery controls;
- 30–90 days: execute recovery, rebuild confidence, and prevent recurrence.

Provide recovery options with cost/schedule/scope tradeoffs, protected outcomes, work to pause, decision rights, daily/weekly cadence, leading indicators, exit criteria, and stakeholder communication drafts. Do not promise recovery dates unsupported by a bottom-up plan and capacity validation.
```

**Illustrative output snapshot:**
> Root cause: decision latency (avg. 9 days per governance decision) — not a resourcing problem. 0–72h: freeze new scope, name a single decision owner. 30–90 days: rebuild trust via two consecutive on-time milestones.
</details>

<details>
<summary><strong>PM-23 · Postmortem and Lessons Learned</strong></summary>

```
Act as a blameless postmortem facilitator. Analyze [INCIDENT/PROJECT EVENT] using the supplied timeline and evidence.

Produce:
- factual impact summary;
- detection, response, containment, recovery, and communication timeline;
- expected versus actual controls;
- contributing factors across people, process, technology, data, vendors, governance, and environment;
- root-cause analysis using Five Whys or a causal tree;
- what worked and what did not;
- corrective and preventive actions with owner, due date, priority, verification evidence, and closure authority;
- lessons to add to standards, templates, training, estimates, and future plans;
- follow-up review date and effectiveness measures.

Avoid hindsight bias and individual blame. Distinguish confirmed evidence from hypotheses. Do not close an action because a document was updated; define evidence that the new control works in practice.
```

**Illustrative output snapshot:**
> Root cause (Five Whys): the monitoring alert threshold was never validated against real production traffic patterns. 3 corrective actions identified, 1 preventive action added directly to the release checklist template.
</details>

<details>
<summary><strong>PM-24 · Roadmap Prioritization</strong></summary>

```
Act as a portfolio and product planning lead. Prioritize the candidate roadmap using the agreed business strategy and constraints.

Inputs: [CANDIDATES, STRATEGIC OBJECTIVES, CUSTOMER EVIDENCE, VALUE, EFFORT, RISK, DEPENDENCIES, CAPACITY, FIXED COMMITMENTS]

Select an appropriate method such as weighted scoring, RICE, WSJF, MoSCoW, or cost of delay and explain why. Show every input, weight, formula, and uncertainty range. Apply mandatory regulatory, security, contractual, and operational work as explicit constraints rather than hiding them inside value scores.

Output:
- ranked roadmap and score breakdown;
- dependency-aware sequencing;
- Now/Next/Later recommendation;
- capacity and funding constraints;
- items deferred and consequence of delay;
- sensitivity analysis and alternative scenario;
- decisions and evidence still required.

Do not let a mathematical score replace strategic judgment. Highlight low-confidence estimates and stakeholder overrides for transparent approval.
```

**Illustrative output snapshot:**
> Method: WSJF. Top-ranked item scores 18.2 (cost of delay 91 ÷ job size 5). 2 items marked mandatory (regulatory) regardless of score. Now/Next/Later split: 4 items in Now, 6 in Next.
</details>

<details>
<summary><strong>PM-24B · Quarterly Program Roadmap Visualization</strong></summary>

**Use when:** Leadership needs a visual, timeline-based roadmap showing workstreams, owners, milestones, dependencies, and risk across quarters — distinct from PM-24's prioritization scoring, this prompt builds the delivery timeline itself.

```
Act as a Senior Program Manager and Portfolio Roadmap Specialist.

Using the project information provided below, create a professional quarterly program roadmap similar to the attached example.

OBJECTIVE

Create a timeline-based roadmap that clearly shows:

* Quarterly timeline: Q1, Q2, Q3, and Q4
* Program workstreams
* Workstream owners
* Initiatives and deliverables
* Start and completion periods
* Key milestones and decision points
* Dependencies between activities
* Risks, blockers, and schedule conflicts
* Current delivery status

INPUT DATA

Program name: [Enter program name]
Program objective: [Enter business objective]
Roadmap period: [Enter start and end dates]
Workstreams: [Enter workstream names]
Owners: [Enter owner for each workstream]
Initiatives and deliverables: [Paste backlog, project plan, Jira export, Excel data, or initiative list]
Known milestones: [Enter milestones]
Known dependencies: [Enter dependencies]
Known risks or constraints: [Enter risks, resource constraints, regulatory dates, or fixed deadlines]
Status date: [Enter reporting date]

ROADMAP STRUCTURE

Organize the roadmap using the following hierarchy:

1. Program-level milestones
2. Workstream
3. Workstream owner
4. Initiative or deliverable
5. Start date
6. Target completion date
7. Dependency
8. Status
9. Risk or blocker

Use one color for each workstream. Display initiatives as horizontal timeline bars and milestones as diamond or star markers.

ANALYSIS REQUIRED

Before creating the roadmap:

1. Review all supplied source information.
2. Identify missing owners, dates, milestones, and dependencies.
3. Detect duplicate or overlapping initiatives.
4. Identify schedule conflicts and unrealistic sequencing.
5. Determine which activities are on the critical path.
6. Flag milestones that may be affected by delayed dependencies.
7. Do not invent missing information.
8. Mark unavailable information as "TBD."
9. Separate confirmed facts from assumptions.
10. Recommend corrections without automatically changing approved dates.

OUTPUT 1: EXECUTIVE SUMMARY

Provide:

* Program objective
* Roadmap period
* Number of workstreams
* Key milestones
* Critical dependencies
* Major risks
* Decisions required from leadership

OUTPUT 2: ROADMAP DATA TABLE

Create a table with these columns:

| Workstream | Owner | Initiative/Deliverable | Start Date | End Date | Quarter | Milestone | Dependency | Status | Risk/Blocker | Confidence |
|---|---|---|---|---|---|---|---|---|---|---|

Use these status values only: Not Started, On Track, At Risk, Blocked, Completed.
Use these confidence values only: High, Medium, Low.

OUTPUT 3: VISUAL ROADMAP

Create a quarterly timeline roadmap with:

* Q1, Q2, Q3, and Q4 across the top
* Workstreams grouped vertically
* Owners shown under each workstream
* Initiatives displayed as timeline bars
* Program and workstream milestones clearly marked
* Dependency arrows between related activities
* Status indicators for on-track, at-risk, blocked, and completed work
* A legend explaining colors, milestone symbols, dependencies, and statuses

If you cannot generate the visual directly, provide the roadmap as a Mermaid Gantt chart and an import-ready CSV table.

OUTPUT 4: VALIDATION REPORT

List:

* Missing information
* Duplicate initiatives
* Date conflicts
* Resource or owner conflicts
* Dependency conflicts
* Milestones without supporting deliverables
* Deliverables without milestones
* Critical-path concerns
* Recommended PM actions

GOVERNANCE REQUIREMENT

Treat the supplied project records as the approved source. Do not change scope, owners, dates, status, or milestones without human approval. Clearly identify every proposed change and include the reason, schedule impact, dependency impact, and required approver.

PROJECT INFORMATION

[PASTE YOUR PROJECT DATA HERE]
```

**Illustrative output snapshot:**

> **Output 1 — Executive Summary**
> Program: AI Claims Assistant Rollout. Objective: reduce manual claims triage time enterprise-wide. Roadmap period: Q1–Q4 2027. 4 workstreams (Data, AI/Engineering, Governance, Adoption). Key milestone: Pilot go/no-go, end of Q2. Critical dependency: Data authorization must close before Q2 build work starts. Major risk: Legal review of source data is currently TBD with no confirmed date. Decision needed from leadership: whether to hold the Q2 milestone or approve a conditional start.
>
> **Output 2 — Roadmap Data Table**
>
> | Workstream | Owner | Initiative/Deliverable | Start Date | End Date | Quarter | Milestone | Dependency | Status | Risk/Blocker | Confidence |
> |---|---|---|---|---|---|---|---|---|---|---|
> | Data | J. Alvarez | Data authorization sign-off | Jan 6 | TBD | Q1 | Yes | None | Blocked | Legal review date unconfirmed | Low |
> | AI/Engineering | M. Chen | Retrieval pipeline build | Feb 3 | Mar 28 | Q1–Q2 | No | Data authorization | Not Started | Depends on blocked item above | Medium |
> | Governance | R. Osei | Evaluation plan approval | Mar 1 | Mar 15 | Q1 | Yes | None | On Track | None | High |
> | Adoption | T. Nguyen | Pilot user training | Apr 1 | Apr 20 | Q2 | No | Retrieval pipeline build | Not Started | Sequencing depends on Eng finishing on time | Medium |
>
> **Output 3 — Visual Roadmap (Mermaid Gantt)**
> ```mermaid
> gantt
>     title AI Claims Assistant Rollout — Quarterly Roadmap
>     dateFormat  YYYY-MM-DD
>     axisFormat  %b
>     section Data
>     Data authorization sign-off (BLOCKED) :crit, data1, 2027-01-06, 45d
>     section AI/Engineering
>     Retrieval pipeline build      :eng1, after data1, 55d
>     section Governance
>     Evaluation plan approval      :milestone, gov1, 2027-03-15, 0d
>     section Adoption
>     Pilot user training           :adopt1, after eng1, 20d
> ```
>
> **Output 4 — Validation Report**
> - Missing information: End date for data authorization is TBD, pending Legal.
> - Date conflict: none detected among confirmed dates.
> - Dependency conflict: Pilot user training is sequenced after a blocked upstream item — recommend flagging as at-risk, not "Not Started."
> - Critical-path concern: Data authorization is the single blocking item for the entire Q1–Q2 sequence; recommend daily follow-up rather than weekly.
> - Recommended PM action: escalate the Legal review date to the sponsor before the next steering update, since it is the root blocker behind three downstream items.

*All names, dates, and figures above are fictional illustrative examples — not real delivery evidence.*
</details>

### 6. AI Program Delivery and Governance

<details>
<summary><strong>AI-PM-01 · AI Use-Case Intake and Risk Triage</strong></summary>

```
Act as an AI governance program manager. Triage the proposed AI use case without granting approval.

Inputs: [INTENDED PURPOSE, USERS, AFFECTED PEOPLE, MODEL/SYSTEM, DATA, OUTPUTS, DECISIONS, AUTONOMY, TOOLS, JURISDICTIONS, VENDOR, BENEFITS]

Assess:
1. Intended purpose, business owner, system owner, users, and affected persons
2. AI technique, model/vendor, data sources, integrations, and deployment context
3. Whether output informs or executes a consequential decision
4. Risk factors: safety, fairness, privacy, security, explainability, reliability, human oversight, third party, regulatory, reputational, and operational
5. Preliminary risk tier and rationale under the organization's method
6. Required reviews, controls, evidence, and approval gates
7. Prohibited or unacceptable operating modes

Output an intake record, missing evidence, preliminary risk classification, control obligations, RACI, and recommendation: discovery, conditional assessment, hold, or reject. Cite authoritative internal policy and current law only when supplied or independently verified. Mark legal interpretation for counsel.
```

**Illustrative output snapshot:**
> Preliminary risk tier: Medium-High (affects credit decisions). Recommendation: conditional assessment — requires bias testing and human-override design before advancing. One data-residency question flagged for legal counsel.
</details>

<details>
<summary><strong>AI-PM-02 · GenAI/RAG Delivery Readiness</strong></summary>

```
Act as a GenAI technical program manager and AI assurance lead. Build a delivery-readiness plan for [GENAI/RAG USE CASE].

Inputs: [INTENDED PURPOSE, ARCHITECTURE, MODEL, RETRIEVAL SOURCES, USERS, DATA CLASSIFICATION, EVALUATION RESULTS, CONTROLS, SLAS]

Evaluate requirements and evidence for:
- source authorization, quality, freshness, chunking, indexing, retrieval, and citations;
- answer relevance, groundedness/faithfulness, completeness, refusal behavior, and uncertainty;
- prompt injection, jailbreak, sensitive-data leakage, harmful content, bias, and access-control tests;
- latency, availability, cost, rate limits, observability, traceability, and rollback;
- human review, feedback, exception, incident, and change-control workflows.

Define test datasets, acceptance thresholds, accountable owners, evidence artifacts, and release gates. Separate offline evaluation, pre-production testing, pilot monitoring, and production monitoring. Recommend Ready, Ready with Conditions, or Not Ready. Never claim that one aggregate score proves safety or compliance.
```

**Illustrative output snapshot:**
> Groundedness score: 87% on the golden set (threshold: 90%) — Not Ready. Recommendation: improve retrieval chunking, then re-test. Prompt-injection tests: passed 18 of 20 adversarial cases.
</details>

<details>
<summary><strong>AI-PM-03 · Agentic AI Deployment Readiness</strong></summary>

```
Act as an agentic AI governance and program delivery lead. Assess an autonomous, tool-using agent before deployment.

Inputs: [AGENT GOAL, AUTONOMY, MODEL, TOOLS/MCP SERVERS, DATA, MEMORY, IDENTITY, CREDENTIALS, ACTIONS, ENVIRONMENT, EVALS, OWNERS]

Map the full plan-decide-act-observe loop. For each tool and action, document permission scope, data accessed, side effects, reversibility, transaction value/impact, rate limit, logging, and approval requirement. Evaluate goal drift, prompt injection, tool misuse, excessive agency, identity/credential scope, memory contamination, cascading failure, multi-agent handoffs, vendor risk, and shutdown/recovery.

Produce:
- autonomy tier and risk classification;
- action-permission matrix;
- mandatory human approval gates;
- least-privilege and segregation-of-duties controls;
- sandbox, simulation, red-team, and failure-injection tests;
- runtime monitoring, anomaly thresholds, kill switch, incident response, and rollback;
- residual risk and deployment recommendation.

Do not authorize production actions. Require accountable human approval for irreversible, external, financial, legal, safety, identity, access, or high-impact decisions.
```

**Illustrative output snapshot:**
> Autonomy tier: L2 (Recommend only). Action-permission matrix: 6 actions require human approval, 2 are pre-approved and reversible. Kill switch tested successfully in sandbox; production kill switch not yet verified — blocking issue.
</details>

<details>
<summary><strong>AI-PM-04 · AI-Assisted PM Output Validation</strong></summary>

```
Act as an independent reviewer of an AI-generated project-management artifact.

Artifact: [PASTE OUTPUT]
Source records: [PASTE/LINK APPROVED SOURCES]
Artifact purpose and decision impact: [DETAILS]

Validate across these dimensions:
1. Factual accuracy and source traceability
2. Completeness against the requested schema
3. Calculation and formula correctness
4. Date, owner, status, and dependency consistency
5. Unsupported assumptions or invented commitments
6. Bias, misleading certainty, or omitted alternatives
7. Confidentiality, privacy, security, legal, and policy concerns
8. Required human approvals and segregation of duties
9. Fitness for the intended audience and decision

Return a finding log with severity, evidence, correction, owner, and disposition. Provide an overall result: Pass, Pass with Corrections, or Fail. Do not rewrite a material finding out of the record; preserve the original, correction, reviewer, and approval trail.
```

**Illustrative output snapshot:**
> Result: Pass with Corrections. One finding: a forecast date was presented with false precision (a single date, no range) — corrected to a 3-scenario range. Source traceability: 9 of 10 claims traced back to a source record.
</details>

<details>
<summary><strong>AI-PM-05 · Prompt Evaluation and Change Control</strong></summary>

```
Act as a prompt governance lead. Evaluate a project-management prompt before it becomes a shared organizational asset.

Prompt and version: [PROMPT]
Intended users/use cases: [DETAILS]
Permitted tools and data: [DETAILS]
Expected output schema: [SCHEMA]
Test cases and reference answers: [DATA]

Assess clarity, task coverage, factuality controls, refusal behavior, prompt-injection resistance, sensitive-data handling, bias, consistency, output validity, tool permissions, approval gates, and traceability. Run or design positive, negative, boundary, adversarial, incomplete-input, conflicting-source, and stale-data tests. Define pass/fail thresholds and capture model/version/settings.

Output a test matrix, findings, proposed changes, regression impacts, residual risks, approval owner, effective date, rollback version, and monitoring plan. Do not promote the prompt based only on a few successful examples. Require revalidation after material changes to the prompt, model, tools, data, policy, or use case.
```

**Illustrative output snapshot:**
> Test matrix: 22 cases (12 positive, 6 adversarial, 4 boundary). 2 failures: the prompt leaked a bracketed placeholder in output under a stale-data test. Recommendation: revise and retest before promoting to a shared asset.
</details>
