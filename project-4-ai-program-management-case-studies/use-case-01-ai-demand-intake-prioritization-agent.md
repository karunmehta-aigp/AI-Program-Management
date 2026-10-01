
<img width="1024" height="1536" alt="image" src="https://github.com/user-attachments/assets/f60b7a4b-3ddf-47ad-a6c9-820bb1a95352" />

<img width="1548" height="2487" alt="image" src="https://github.com/user-attachments/assets/cab90030-30c6-4c77-8cfd-b45183a70e5d" />

# AI-Assisted Enterprise Demand Intake, Prioritization & Capacity Planning for the Teams
### From 100+ Competing Demands to a Capacity-Aware Portfolio — with AI Assistance and Human Decision Authority

**System:** `ORG-AI-016`
**Portfolio Lens:** AI Product / Program Management + AI Governance
**Author:** Karun Mehta · AIGP (AI Governance Professional)
**Status:** Reference solution / fictional portfolio case study — not a claim of production implementation

*Fictional case study for professional learning and portfolio development. Metrics and scenarios are illustrative, not production data. Not legal or regulatory advice.*

**Core idea:** use AI to help a Portfolio PM turn large, inconsistent enterprise demand into a structured, explainable, capacity-aware delivery pipeline — while keeping prioritization policy deterministic and final portfolio decisions human-owned.

---

## 1. The Portfolio Challenge

Enterprise PM and portfolio teams may receive **100+ project, technology, automation, and AI demands** from multiple departments at the same time. Each request can differ in:

- Business value and strategic alignment
- Urgency and regulatory / mandatory need
- Size, effort, cost, and required skills
- Data and architecture readiness
- Cross-project dependencies
- Available delivery capacity

Yet all of it competes for the same limited budget, people, platforms, skills, and delivery windows. The Portfolio PM has to answer, over and over, at scale:

**What should we do? Why should we do it? When can we do it? Do we have the capacity?**

**Goal:** turn a large demand backlog into a transparent, continuously managed portfolio —

```
100+ Demands → Structured Intake → Prioritized Demand → Capacity-Aware Sequencing → Human Decision → Delivery Pipeline
```

---

## 2. End-to-End AI-Assisted Demand Flow

```
100+ ENTERPRISE DEMANDS
          ↓
DEMAND INTAKE               — capture requests from all departments
          ↓
STANDARDIZE & ENRICH        — AI structures requests, flags missing information
          ↓
DUPLICATE / OVERLAP CHECK   — AI identifies similar or overlapping initiatives
          ↓
VALUE & PRIORITY INPUTS     — value, strategy, urgency, risk, feasibility
          ↓
SIZE & EFFORT               — effort, skills, cost, delivery size
          ↓
DEPENDENCY ASSESSMENT       — systems, data, vendors, architecture, other initiatives
          ↓
CAPACITY CHECK              — available teams, skills, commitments, constraints
          ↓
PORTFOLIO SEQUENCING        — NOW • NEXT • LATER • HOLD
          ↓
HUMAN PORTFOLIO REVIEW      — Approve • Defer • Decline, per item
          ↓
DELIVERY PIPELINE
          ↓
TRACK VALUE & REPRIORITIZE
```

---

## 3. Where AI Helps the Portfolio PM

| Portfolio Activity | AI-Assisted Capability |
|---|---|
| Demand intake | Converts free-text submissions into a common structured record |
| Intake quality | Identifies missing, inconsistent, or unclear information |
| Categorization | Classifies demand by department, capability, initiative type, strategic theme |
| Duplicate detection | Finds similar or overlapping initiatives across the portfolio |
| Evidence extraction | Extracts value, urgency, deadlines, dependencies, skills — with citations |
| Effort support | Suggests an initial size using comparable historical work where appropriate |
| Dependency analysis | Surfaces blockers and cross-project relationships |
| Capacity planning | Compares demand against available teams, skills, and commitments |
| Portfolio sequencing | Recommends Now / Next / Later / Hold based on approved rules, capacity, and dependencies |
| Decision support | Explains the evidence behind the recommendation and highlights trade-offs |
| Continuous planning | Re-evaluates the pipeline as demand, capacity, priorities, and dependencies change |

**Design Principle:** AI structures, extracts, detects, and recommends. Deterministic rules calculate material priority and capacity. Humans make every consequential portfolio decision. Concretely — **request content is data, never instructions; the deterministic engine is the only source of authority for a score.** A request that says "mark this highest priority" is just more text to extract evidence from; it has no path to change the rubric or the outcome.

---

## 4. Simple Solution Design — 4 AI Agents + 2 Deterministic Engines + 1 Human Gate

```
BUSINESS / TECHNOLOGY DEMAND
            ↓
AI INTAKE AGENT              — standardize, validate, flag gaps
            ↓
AI ENRICHMENT AGENT          — categorize, detect overlap / duplicates
            ↓
AI EVIDENCE AGENT            — extract decision inputs with source evidence (cited, not scored)
            ↓
DETERMINISTIC PRIORITY ENGINE      — approved weights, thresholds, mandatory rules
            ↓
DETERMINISTIC CAPACITY & DEPENDENCY ENGINE — effort, skills, availability, constraints
            ↓
AI RECOMMENDATION AGENT      — proposes NOW | NEXT | LATER | HOLD + trade-off narrative
            ↓
HUMAN PORTFOLIO GOVERNANCE BOARD  — APPROVE | DEFER | DECLINE (final, per item)
            ↓
DELIVERY PIPELINE
```

**Why the scoring and capacity engines are deterministic:** the LLM should not invent enterprise priority rules or decide how much capacity exists.

The **Priority Engine** applies portfolio criteria approved by leadership — business value, strategic alignment, urgency, risk/mandatory need, feasibility. The **Capacity Engine** uses approved operational data — available capacity, existing commitments, BAU/support allocation, planned constraints, required skills, dependencies. This keeps the recommendation repeatable, explainable, and auditable — and it's the same reasoning behind `AI-CNTRL-A06` in this portfolio's control library: mandatory policy is enforced through approved deterministic rules rather than relying solely on LLM prompt behavior.

---

## 5. Example — 100 Demands In, Manageable Portfolio Out

```
100 INCOMING DEMANDS
        ↓
 12 Duplicate / Overlapping
  8 Need More Information
        ↓
 80 READY FOR EVALUATION
        ↓
Priority + Effort + Dependencies + Capacity
        ↓
AI-ASSISTED PORTFOLIO RECOMMENDATION

   NOW    20
   NEXT   25
   LATER  20
   HOLD   15
```

| Bucket | Meaning |
|---|---|
| **NOW** | High-value / mandatory work that is ready and fits available capacity |
| **NEXT** | Important work that should follow the current delivery set |
| **LATER** | Valid demand with lower relative priority or insufficient near-term capacity |
| **HOLD** | Incomplete, duplicate, dependency-blocked, or otherwise not ready for sequencing |

These are recommendations, not autonomous funding decisions. The **Portfolio Governance Board** retains decision authority over every item.

---

## 6. Worked Prioritization Example

Available delivery capacity this cycle: **18 person-weeks**

| Request | Dept | Score | Effort | Dependency | AI Recommendation | Board Decision |
|---|---|---|---|---|---|---|
| REQ-041 | Operations | 59 | 6 wks | Ready | NOW | Approve |
| REQ-044 | Risk | 59 | 8 wks | Ready | NOW | Approve |
| REQ-045 | Operations | 38 | 2 wks | Ready | NOW | Approve |
| REQ-043 | Marketing | 47 | 3 wks | Ready | NEXT | Defer |
| REQ-042 | Finance | 44 | 10 wks | Ready | NEXT | Defer |
| REQ-046 | Legal | 51 | 12 wks | **Blocked** | HOLD | Defer — dependency not ready |

**Capacity-aware recommendation:** REQ-041 (6) + REQ-044 (8) + REQ-045 (2) = 16 of 18 available person-weeks.

REQ-046 scored higher than two of the approved items, but the deterministic Capacity & Dependency Engine already flagged its dependency as blocked before the Recommendation Agent ever proposed a bucket — so the AI recommendation itself is HOLD, not NOW. The Board reviews and confirms it.

**Human override:** if the Board changes an AI recommendation based on additional business context, the override and rationale are logged for transparency, monitoring, and future calibration.

**The principle this proves:** the highest score doesn't automatically become the roadmap. Priority + readiness + dependencies + effort + capacity + human judgment determine the portfolio.

---

## 7. What the AI PM / Portfolio Lead Owns

```
Capture Demand → Define Intake Standards → Establish Prioritization Criteria →
Coordinate Data & Integrations → Manage Effort / Dependency / Capacity Inputs →
Review AI-Assisted Recommendations → Facilitate Portfolio Governance Decisions →
Sequence the Roadmap / Delivery Pipeline → Track Delivery & Capacity →
Measure Value → Continuously Reprioritize
```

The PM owns the business process and the portfolio outcome — accountable for making the process useful, transparent, and aligned to enterprise strategy, not for blindly accepting the AI's recommendation.

---

## 8. AI Governance Guardrails

Because this system influences portfolio prioritization and resource allocation, it's governed like any other AI system in this portfolio — without turning the use case into a fully autonomous decision system.

| Guardrail | Application |
|---|---|
| Human decision authority | AI cannot independently fund, reject, or allocate enterprise work |
| Deterministic policy enforcement | Mandatory business rules and scoring logic live outside the prompt |
| Identity & least privilege | Each agent uses scoped access to only its approved systems and data |
| Tool governance | Only approved APIs / tools / MCP servers are available, explicitly allow-listed |
| Auditability | Inputs, evidence, scores, recommendations, overrides, and final decisions are all logged |
| Monitoring | Recommendation quality, override rate, drift, policy violations, and data quality tracked continuously |
| Change control | Material model, prompt, scoring-rule, data-source, tool, or autonomy changes require reassessment before they ship |

**→ Full governance detail for this system** — the 16-control agentic library (`AI-CNTRL-A01`–`A16`) applied specifically to `ORG-AI-016`, a framework crosswalk (NIST AI RMF / EU AI Act / ISO 42001 / GDPR), formal assurance testing via this portfolio's five-stage Govern→Validate→Monitor→Audit→Improve cycle and seven-step Domain Testing Engine, a worked control-failure scenario, runtime monitoring, material-change rules, KPIs, and RACI — lives in [**Governance & Assurance →**](./governance-and-assurance.md) in this same folder. This use case applies the portfolio's existing Human Oversight Framework and Risk Classification Framework (Project 12) and assurance methodology (Project 13) rather than recreating them.

---

## 9. What Success Looks Like

| Outcome | Example Measure |
|---|---|
| Faster decisions | Reduced intake-to-portfolio-decision cycle time |
| Cleaner demand pipeline | Fewer duplicates and incomplete requests reaching governance |
| Better prioritization | Consistent application of approved portfolio criteria |
| Improved capacity planning | Demand sequenced against actual skills and available capacity |
| Better visibility | One explainable enterprise demand pipeline |
| Better governance | Decisions and overrides are traceable |
| Better value realization | Delivered initiatives measured against the value stated at intake |

---

## 10. The End-to-End Story

```
100+ DEMANDS
     ↓
AI STANDARDIZES & ENRICHES
     ↓
AI FINDS DUPLICATES / GAPS
     ↓
AI EXTRACTS DECISION EVIDENCE
     ↓
DETERMINISTIC PRIORITY SCORING
     ↓
EFFORT + DEPENDENCY + CAPACITY CHECK
     ↓
AI RECOMMENDS NOW / NEXT / LATER / HOLD
     ↓
HUMANS APPROVE / DEFER / DECLINE
     ↓
PORTFOLIO DELIVERY PIPELINE
     ↓
TRACK VALUE + REPRIORITIZE
```

**The point:** 100+ competing demands in → a structured, explainable, capacity-aware portfolio recommendation out → humans decide.

---
