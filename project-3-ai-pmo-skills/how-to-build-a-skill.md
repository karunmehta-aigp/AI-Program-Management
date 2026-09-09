# How to Build a Skill

**Author:** Karun Mehta · AIGP · PMP

> **This page is a guide, not an installable skill.** It teaches how to build a skill for the [AI-PMO Skills catalog](https://github.com/karunmehta-aigp/AI-Program-Management/blob/main/project-3-ai-pmo-skills/README.md); it doesn't begin with its own YAML frontmatter, so it can't be uploaded or activated on its own. If you're looking for an actual skill to install, see the [Skills Matrix](https://github.com/karunmehta-aigp/AI-Program-Management/blob/main/project-3-ai-pmo-skills/README.md#skills-matrix).

> **Status: I am still building these skills.** This page documents my working method for turning a repeatable AI-PMO workflow into a proper skill — it is a personal reference for how I approach the process, not a claim that the skills catalogued in this project have already been built, tested, or deployed.

---

## 1. What Is a Skill?

A prompt in [Project 2 Prompt Library](https://github.com/karunmehta-aigp/AI-Program-Management/tree/main/project-2-ai-prompts) is something a program manager pastes in when they need it. A skill is different: it's packaged so Claude recognizes *on its own* when a task matches, and it arrives with everything needed to do that task well — not just an instruction, but the reference material and reusable assets a specialist would bring to the job.

A prompt is a question you ask an expert. A skill is hiring that expert and giving them their reference binder, their templates, and their standard checklist, so they don't start from zero every time.

---

## 2. Five-Minute Beginner Quick Start

Before touching folders, scripts, or references, build the smallest possible version first — one file, nothing else:

```
my-first-skill/
└── SKILL.md
```

That's it. A first skill does not need `scripts/`, `references/`, or `assets/`. Anthropic's own guidance is to start with simple Markdown instructions and add complexity only once you actually need it — most beginners over-build their first skill by adding folders they don't need yet.

---

## 3. A Minimal SKILL.md Example

Here's the smallest real skill that actually works — copy this, change the name and description, and you have a working first skill:

```markdown
---
name: resource-capacity-allocator
description: Allocate team capacity to prioritized work. Use for staffing conflicts, resource availability, capacity planning, or competing release demands.
---

# Resource Capacity Allocator

## Purpose
Match available team capacity against prioritized work and surface conflicts.

## How to Execute
1. Confirm the work items, required skills, and time period.
2. Confirm each team member's availability and existing commitments.
3. Calculate gross capacity, deductions, and net capacity.
4. Flag conflicts — over-allocation, key-person risk, skill gaps.
5. Present allocation options; do not finalize assignments without manager confirmation.

## Human Control Point
The responsible manager confirms final availability and approves the allocation. This skill drafts options; it does not assign people.
```

That's a complete, working skill. Everything after this section explains *why* it's built this way and how to grow it as the task gets more complex.

---

## 4. How Metadata Actually Works

The two-line YAML block at the top — `name` and `description` — is the single most important part of the file, because it's the *only* part Claude sees before deciding whether to use the skill at all. Everything below it stays invisible until the description earns its attention.

**Weak description (too vague to trigger reliably):**
```yaml
description: Helps with resource planning.
```
This could mean almost anything, and won't reliably fire on "who's available for the Q4 release."

**Strong description (specific about what and when):**
```yaml
description: Allocate team capacity to prioritized work. Use for staffing conflicts, resource availability, capacity planning, or competing release demands.
```
This names the concrete task *and* the actual phrases someone would type.

**On length:** For Claude.ai custom skills, keep the description within 200 characters. State what the skill does and when it should be used. Put the most important trigger terms near the beginning. (Note: the broader Agent Skills specification used for API/platform skills allows up to 1,024 characters — but skills uploaded through Claude.ai must use the shorter 200-character limit.) The example above is concise enough.

**One habit worth keeping:** write a direct description that clearly states what the skill does and when Claude should use it, with real trigger phrases included directly rather than just a topic area. Third-person wording is not required — the example above uses direct, imperative phrasing ("Allocate team capacity... Use for staffing conflicts...") and that's perfectly fine.

---

## 5. Optional Folders (Add Only When You Need Them)

Once a skill's instructions get long, or the same reference material or code keeps getting rewritten, that's the signal to add structure:

```
skill-name/
├── SKILL.md                 (required)
├── scripts/                  (optional — code that runs the same way every time)
├── references/               (optional — material to consult while working)
└── assets/                   (optional — files that end up in the output, not read as instructions)
```

**`scripts/`** holds anything that should run identically every time rather than being re-derived from scratch — for `budget-forecast-finops`, that might be the EAC/variance calculation logic, so the math is deterministic instead of freshly reasoned each run.

**`references/`** holds material Claude should consult but doesn't need memorized upfront — for `data-readiness-lineage`, a data-classification policy; for `regulatory-change-coordinator`, an obligations checklist per jurisdiction. This loads only when the skill actually needs it.

**`assets/`** holds files used *in* the output rather than read as guidance — a report template, a slide master. `executive-steering-dashboard` might ship a `.pptx` template here so the output looks consistent every time.

**One rule that keeps this clean:** the same fact should never live in both `SKILL.md` and a `references/` file. If it's core to how the skill runs, it belongs in `SKILL.md`. If it's detail only needed sometimes, it belongs in `references/`.

### How Loading Actually Works

| Stage | What Claude loads | Suggested size | When loaded |
|---|---|---|---|
| 1. Metadata | Name and description | Keep concise | Used to identify the skill |
| 2. Instructions | `SKILL.md` body | Ideally under approximately 500 lines | Loaded when the skill is selected |
| 3. Resources | Scripts, references, and assets | Add only when needed | Accessed during execution |

Add resources deliberately, not by default — every extra file is something to maintain, and an unnecessary `references/` folder doesn't make a skill more credible, just harder to keep accurate.

---

## 6. Step-by-Step Creation Process

This is the sequence I use for turning an idea from the [Skills Matrix](https://github.com/karunmehta-aigp/AI-Program-Management/blob/main/project-3-ai-pmo-skills/README.md#skills-matrix) into an actual skill.

**1. Pin down real trigger phrases with concrete questions.**
Before writing anything, ask direct questions — of yourself or whoever requested the skill — one at a time rather than all at once:
- "What should this skill actually do — just one thing, or a few related things?"
- "What would someone literally type that should trigger this?"
- "Give me a real example of when you'd reach for this."

For `resource-capacity-allocator`, that's not "help with resources" — it's "capacity conflict," "who is available," "resolve Q4 staffing." Vague triggers make a skill fire at the wrong times or never fire at all.

**2. Work backward from one real example to find what's reusable.**
Take one concrete trigger and mentally run it end to end. For `model-evaluation-governance` responding to "create an evaluation plan for a RAG assistant," the repeated pain point isn't the writing — it's re-deriving the same evaluation-layer taxonomy (offline, pre-production, pilot, production) every single time. That taxonomy belongs in a `references/` file, not reinvented per run.

**3. Start with one file. Add folders only when the workflow genuinely needs them.**
Begin with `SKILL.md` alone, following the minimal example in Section 3. Add `references/`, `scripts/`, or `assets/` only once you can point to a specific piece of content that keeps getting rewritten or re-explained.

**4. Write `SKILL.md` in plain, instructional language.**
Use direct, verb-first instructions — "confirm the risk tier before proceeding," not "you should probably check the risk tier." Every skill should answer three things plainly: what it's for, when it fires, and exactly how it uses whatever's in `scripts/`, `references/`, or `assets/`.

Here's a blank template following that shape:

```markdown
---
name: skill-name-here
description: [What it does]. Use when [the specific trigger situations, in the user's own likely words].
---

# [Skill Name, Human-Readable]

## Purpose
[One to three sentences: what this skill produces and for whom.]

## When to Use
- [Trigger scenario 1]
- [Trigger scenario 2]

**Don't use for:** [The nearby task this skill should NOT handle — helps Claude route correctly.]

## How to Execute This Skill
1. [Confirm required inputs — list them explicitly.]
2. [Reference material to consult, if any — e.g., "read references/x.md for the scoring formula."]
3. [The core workflow steps, in order.]
4. [What to flag rather than invent, per the Standard Skill Contract.]

## Output
[Exact format: a table, a specific set of fields, a file type.]

## Human Control Point
[Named per the Accountability Model — what this skill drafts/recommends vs. what a human must approve.]
```

**5. Bake in the control boundary, every time.**
Every skill here follows the [Standard Skill Contract](https://github.com/karunmehta-aigp/AI-Program-Management/blob/main/project-3-ai-pmo-skills/README.md#standard-skill-contract) — confirm inputs rather than invent them, produce a recommendation rather than a decision, and name the human control point explicitly. This isn't optional polish; it's the difference between a skill that's safe to deploy in an investment-banking PMO and one that isn't.

---

## 7. Packaging and Uploading

Once `SKILL.md` (and any supporting folders) are ready, here's how to get a skill onto Claude.ai:

1. Place `SKILL.md` inside a folder named exactly after the skill.
2. Confirm the folder name matches the `name` field in the frontmatter.
3. ZIP the complete folder (not just the file inside it).
4. Open Claude.
5. Go to **Customize → Skills** (menu naming may vary by plan — Team/Enterprise admins may see this under Organization settings instead; check Claude's current interface if it doesn't match exactly).
6. Click the **"+"** button, then **"+ Create skill,"** then **"Upload a skill."**
7. Upload the ZIP file.
8. Toggle the skill on.
9. Test it with several realistic prompts before relying on it.

The ZIP needs the folder *inside* it, not just the file at the top level:

```
resource-capacity-allocator.zip
└── resource-capacity-allocator/
    └── SKILL.md
```

A ZIP containing just a loose `SKILL.md` with no enclosing folder will not install correctly.

---

## 8. Testing Checklist

Before treating any skill as finished, run through this:

- [ ] Does the `description` alone make it obvious when to use this skill, with real trigger phrases rather than a vague topic area?
- [ ] Is anything duplicated between `SKILL.md` and a `references/` file? If so, delete it from one place.
- [ ] Does the instructions body stay under roughly 500 lines, or has detail crept in that should have moved to `references/`?
- [ ] Is the writing verb-first and instructional throughout, not second-person or hedging?
- [ ] Does the skill name a specific human control point, per the Standard Skill Contract — not just "a human reviews this"?
- [ ] If there's a `scripts/` file, does `SKILL.md` actually reference it, so Claude knows it exists and when to run it?
- [ ] Have you tested it with at least 3–5 realistic prompts, including one that should *not* trigger it, to check it doesn't fire too broadly?

---

## 9. PMO Governance and Security Controls

Beyond the Standard Skill Contract, a few security-specific rules apply to anything going into this catalog:

- **Never store credentials or confidential information inside a skill, whether the skill is private or shared.** This includes passwords, API keys, tokens, and confidential client information.
- **Review scripts before enabling any downloaded or third-party skill.** A script can execute code within Claude's permitted environment, so inspect it before enabling the skill.
- **Confirm authorization before a skill updates any external system.** Drafting a recommendation is different from taking an action — the Accountability Model in the main README exists precisely to keep that line visible.
- **Use sanitized, fictional examples when publishing skills to GitHub or any public repository.** Never use real client names, real figures, or real deal data in an illustrative snapshot — every example in this project's prompts and skills is fictional for exactly this reason.

---

## 10. Worked Example: Designing `raid-decision-manager`

To make the process in Section 6 concrete, here's how it plays out for one skill from the catalog.

- **Trigger phrases identified:** "RAID," "decision log," "issue review"
- **Reusable content identified:** the risk-scoring formula (probability × impact, 1–5 scale) and the four-category classification logic (Risk / Assumption / Issue / Dependency) are the same every time — these become a short `references/raid-classification.md` rather than being re-explained in every run
- **`SKILL.md` body, in brief:** confirm which source records are supplied (status reports, meeting notes, prior RAID log); classify each item; score risks using the reference formula; flag anything marked "closed" without supporting evidence and recommend it for reopening; output the updated register plus a short escalation list
- **Control boundary:** the skill never accepts risk or closes an item on its own authority — it drafts the updated register and flags exposures; the named risk owner and governance forum make the actual accept/close decision, exactly as described in the [Accountability Model](https://github.com/karunmehta-aigp/AI-Program-Management/blob/main/project-3-ai-pmo-skills/README.md#accountability-model)
- **What would go in `assets/` (if needed):** a RAID log spreadsheet template, so the output drops into the same format the PMO already uses

That's the whole loop — real triggers, one worked example, extract what repeats, write it down once, keep the human decision explicit.

---

## 11. Official Resources

- [How to create custom skills](https://support.claude.com/en/articles/12512198-how-to-create-custom-skills)
- [Extend Claude Code with skills](https://code.claude.com/docs/en/skills)
- [Anthropic's example skills](https://github.com/anthropics/skills)

Check these directly for the current interface names and limits — product surfaces and exact menu paths change over time, and this guide's Section 7 steps should be verified against whatever Claude's interface shows at the time you're using it.

---

## Source Note

The SKILL.md format itself — YAML frontmatter, the `scripts/` / `references/` / `assets/` split, and the progressive-disclosure loading model — follows Anthropic's public Claude Skills documentation. The process steps, the metadata examples, the fill-in template, the testing checklist, the security controls, and the `raid-decision-manager` worked example on this page are original, written for this project's own investment-banking and enterprise AI-PMO context.

---

*This guide describes my own working method for the skills catalogued in this project, adapted for an investment-banking and enterprise AI-PMO context — not a general-purpose skill-authoring reference.*
