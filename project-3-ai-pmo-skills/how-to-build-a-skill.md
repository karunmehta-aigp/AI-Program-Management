# How to Build a Skill

**Author:** Karun Mehta · AIGP · PMP

> **Status: guidance document.** This explains the approach I'm using to design the skills catalogued in this project's README. It is a personal reference for how to turn a repeatable AI-PMO workflow into a proper skill — not a claim that every skill listed has already been built this way.

---

## Why a Skill Is Different from a Prompt

A prompt in [Project 2](../project-2-ai-prompts/) is something a program manager pastes in when they need it. A skill is different: it's packaged so Claude recognizes *on its own* when a task matches, and it comes with everything needed to do that task well — not just an instruction, but the procedural know-how, reference material, and reusable assets a specialist would bring to the job.

Think of the difference this way: a prompt is a question you ask an expert. A skill is hiring that expert and giving them their reference binder, their templates, and their standard checklist — so they don't start from zero every time.

---

## What a Skill Is Made Of

Every skill in this catalog is built from one required file and three optional supporting folders:

```
skill-name/
├── SKILL.md                 (required)
│   ├── name + description   (short metadata, always visible)
│   └── instructions          (the workflow itself)
├── scripts/                  (optional — code that runs the same way every time)
├── references/               (optional — material to consult while working)
└── assets/                   (optional — files that end up in the output, not read as instructions)
```

**`SKILL.md`** is the only required piece. Its two-line metadata block — `name` and `description` — is what tells Claude *when* to reach for this skill at all, so it has to be specific and written from Claude's point of view ("this skill should be used when…"), not a marketing blurb.

**`scripts/`** holds anything that should run identically every time rather than being re-derived from scratch — for a skill like `budget-forecast-finops`, that might be the EAC/variance calculation logic, so the math is deterministic instead of freshly reasoned each run.

**`references/`** holds material Claude should consult but doesn't need memorized upfront — for `data-readiness-lineage`, that could be a data-classification policy document; for `regulatory-change-coordinator`, an obligations checklist per jurisdiction. These load only when the skill actually needs them, which keeps the core instructions lean.

**`assets/`** holds files that get used *in* the output rather than read as guidance — a report template, a logo, a slide master. `executive-steering-dashboard` might ship a `.pptx` template here so the output looks consistent every time rather than reinvented.

**One rule that keeps this clean:** the same fact should never live in both `SKILL.md` and a `references/` file. If it's core to how the skill runs, it belongs in `SKILL.md`. If it's detail Claude only needs sometimes, it belongs in `references/` — otherwise `SKILL.md` turns into a dumping ground and gets slower and harder to trust.

---

## Why the Split Actually Matters

This isn't just tidiness — it's a context budget problem. A skill loads in three stages, and only the first stage is "free":

| Stage | What loads | Roughly how much | When |
|---|---|---|---|
| 1. Metadata | `name` + `description` only | ~100 words | Always present, for every skill in the catalog |
| 2. Instructions | The body of `SKILL.md` | Under ~5,000 words | Only once the skill actually triggers |
| 3. Bundled resources | `scripts/`, `references/`, `assets/` | No practical limit | Only when the running skill decides it needs them |

A script is the cheapest of all — it can be *executed* without ever being read into context, which is exactly why deterministic, repeated logic (a calculation, a formatting rule) belongs there rather than being re-explained in prose every time.

---

## Building One, Step by Step

This is the sequence I use for turning an idea from the [Skills Matrix](./README.md#skills-matrix) into an actual skill.

**1. Pin down real trigger phrases first.**
Before writing anything, get concrete about what someone would actually type. For `resource-capacity-allocator`, that's not "help with resources" — it's "capacity conflict," "who is available," "resolve Q4 staffing." Vague triggers make a skill fire at the wrong times or never fire at all.

**2. Work backward from one real example to find what's reusable.**
Take one concrete trigger and mentally run it end to end. For `model-evaluation-governance` responding to "create an evaluation plan for a RAG assistant," the repeated pain point isn't the writing — it's re-deriving the same evaluation-layer taxonomy (offline, pre-production, pilot, production) every single time. That taxonomy belongs in a `references/` file, not reinvented per run.

**3. Scaffold before writing prose.**
Set up the folder structure first — `SKILL.md` plus whichever of `scripts/`, `references/`, `assets/` the skill actually needs — before drafting instructions. It's easier to write focused instructions against a structure that already exists than to structure things after the fact.

**4. Write `SKILL.md` in plain, instructional language.**
Use direct, verb-first instructions — "confirm the risk tier before proceeding," not "you should probably check the risk tier." This isn't a style preference; it reads more reliably to Claude than second-person hedging does. Every skill in this catalog should answer three things plainly: what it's for, when it fires, and exactly how it uses whatever's in `scripts/`, `references/`, or `assets/`.

**5. Bake in the control boundary, every time.**
Every skill here follows the [Standard Skill Contract](./README.md#standard-skill-contract) — confirm inputs rather than invent them, produce a recommendation rather than a decision, and name the human control point explicitly. This isn't optional polish; it's the difference between a skill that's safe to deploy in an investment-banking PMO and one that isn't.

**6. Validate before calling it done.**
Before treating a skill as finished, check it against the same bar as everything else in this catalog: does the metadata alone make the trigger obvious? Is there anything duplicated between `SKILL.md` and a reference file? Does the instructions body stay under a reasonable length, or has detail crept in that should have moved to `references/`?

**7. Run it, then fix what actually broke.**
The most useful feedback comes from watching a skill handle a real (or realistic fictional) case and noticing exactly where it stumbled — not from guessing in advance. Update `SKILL.md` or the bundled resources based on that specific failure, then run it again.

---

## A Worked Example: Designing `raid-decision-manager`

To make this concrete, here's how the process above actually plays out for one skill from the catalog.

- **Trigger phrases identified:** "RAID," "decision log," "issue review"
- **Reusable content identified:** the risk-scoring formula (probability × impact, 1–5 scale) and the four-category classification logic (Risk / Assumption / Issue / Dependency) are the same every time — these become a short `references/raid-classification.md` rather than being re-explained in every run
- **`SKILL.md` body, in brief:** confirm which source records are supplied (status reports, meeting notes, prior RAID log); classify each item; score risks using the reference formula; flag anything marked "closed" without evidence and reopen it; output the updated register plus a short escalation list
- **Control boundary:** the skill never accepts risk or closes an item on its own authority — it drafts the updated register and flags exposures; the named risk owner and governance forum make the actual accept/close decision, exactly as described in the [Accountability Model](./README.md#accountability-model)
- **What would go in `assets/` (if needed):** a RAID log spreadsheet template, so the output drops into the same format the PMO already uses

That's the whole loop — real triggers, one worked example, extract what repeats, write it down once, keep the human decision explicit.

---

*This guide describes my own working method for the skills catalogued in this project, adapted for an investment-banking and enterprise AI-PMO context — not a general-purpose skill-authoring reference.*
