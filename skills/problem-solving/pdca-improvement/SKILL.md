---
name: pdca-improvement
description: >-
  Run a PDCA cycle, Plan Do Check Act improvement cycle, or structured improvement project.
  Guides through problem analysis, piloting, verification, and standardisation. Distinguished
  from 8D: PDCA is for proactive improvement initiatives, 8D is for reactive defect response.
  Use for process optimisation, lessons learned implementation, and quality objectives.
license: MIT
metadata:
  author: RBraga01
  version: "1.0"
  iso-9001: "10.3"
  iatf-16949: "10.3.1"
  domain: quality-engineering
  subdomain: problem-solving
  industries: automotive,electronics,aerospace,medical,general
---

# PDCA Improvement Cycle

## When to use

Use PDCA for:
- Continuous improvement initiatives (not problem reactions — use 8D for that)
- Implementing a process optimisation with uncertain outcome
- Piloting a change before full deployment
- Structured improvement from lessons learned or audit findings
- Meeting a quality objective that requires a new approach

**Key distinction from 8D:** PDCA is proactive or slow-burn improvement. 8D is reactive to a specific defect or failure. Both use root cause analysis, but PDCA has a broader scope and a pilot step before full deployment.

## Prerequisites

- Improvement goal defined (with target metric)
- Baseline data available (current performance)
- Owner and resources assigned

## Workflow

### PLAN — Analyse and define the approach

1. **Define the current situation**
   - What is the problem or improvement opportunity?
   - What is the current measured performance? (baseline)
   - What is the target? (SMART: Specific, Measurable, Achievable, Relevant, Time-bound)

2. **Analyse root cause**
   - Use [Fishbone](../fishbone-analysis/) and [5-Why](../5why-root-cause/) to understand why current performance is below target
   - Use data: Pareto charts, run charts, capability studies

3. **Develop the improvement plan**
   - What specific actions will close the gap?
   - Who is responsible for each action?
   - What is the timeline?
   - What resources are needed?
   - What risks does the change introduce? (FMEA check)

4. **Define the pilot scope**
   - Which process, line, or area will pilot the change?
   - What volume / duration is needed to validate effectiveness?
   - What will you measure, and how?

**Plan gate:** Is the root cause understood? Is the pilot scope defined? Is success measurable?

---

### DO — Implement (pilot)

1. Implement the planned changes in the pilot scope only
2. Train affected personnel
3. Execute and collect data during the pilot
4. Document what actually happened vs. what was planned (deviations are data)

**Do not deploy broadly at this stage.** The pilot is to learn, not to commit.

---

### CHECK — Verify results

Compare pilot results against the Plan targets:

| Metric | Baseline | Target | Pilot result | Gap closed? |
|--------|----------|--------|--------------|-------------|
| [KPI 1] | | | | |
| [KPI 2] | | | | |

Ask:
- Did the change produce the expected improvement?
- Were there any unexpected negative effects?
- Is the improvement sustainable (stable over time) or a one-time effect?
- Was the pilot conducted under representative conditions?

**Check gate:**
- If target met → proceed to Act (standardise)
- If partially met → revise Plan, run another Do-Check cycle
- If not met → return to Plan, re-analyse root cause

---

### ACT — Standardise or revise

**If the pilot succeeded:**

1. Update process documents: work instructions, control plan, PFMEA
2. Deploy to all applicable areas (horizontal deployment)
3. Train all affected personnel
4. Set up ongoing monitoring to confirm the improvement holds
5. Share lessons learned

**If the pilot failed or was inconclusive:**

1. Document what was learned
2. Revise the Plan (new root cause hypothesis or new approach)
3. Repeat the cycle

**Do not standardise an unverified change.** Standardising a failed pilot permanently embeds the problem.

---

## Gate summary

| Gate | Key question | Pass criterion |
|------|-------------|----------------|
| Plan | Is root cause understood and pilot scoped? | Root cause confirmed, target measurable, pilot defined |
| Do | Was the pilot conducted as planned? | Actions implemented, data collected |
| Check | Did the change achieve the target? | Target metric met or exceeded in pilot |
| Act | Are documents updated and deployment complete? | All affected documents revised, training done |

## Common mistakes

- **Skipping Plan** — jumping straight to Do without understanding root cause
- **Skipping Check** — deploying broadly after pilot without verifying data
- **Treating Act as permanent before Check** — standardising before the pilot result is confirmed
- **One cycle only** — PDCA is a cycle; if the first cycle doesn't solve it, run another
- **Using PDCA for urgent defects** — for customer complaints or safety issues, use 8D instead

## Output Format

At the start of each use, ask the user:

> "How would you like to receive the output?
> **A** — Structured Markdown (formatted tables and sections, ready to copy)
> **B** — Plain tables (simplified structure for Excel or Word)
> **C** — Narrative report (flowing text for a formal document or email)
>
> Default: A."

Adapt all output sections to the chosen format. If the platform or session context already defines a format preference, skip this question.
