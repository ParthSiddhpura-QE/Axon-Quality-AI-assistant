---
name: 8d-problem-solving
description: >-
  Structured 8 Disciplines (8D) problem-solving methodology for quality failures, customer
  complaints, and non-conformances. Covers D0 emergency response through D8 team recognition.
  Use when a defect, complaint, or quality escape requires documented root cause analysis and
  permanent corrective action — especially for automotive OEM customer requirements.
license: MIT
metadata:
  author: RBraga01
  version: "1.0"
  iso-9001: "10.2"
  iatf-16949: "10.2.3"
  domain: quality-engineering
  subdomain: problem-solving
  industries: automotive,electronics,aerospace,medical,general
---

# 8D Problem Solving

## When to use

Use 8D for customer-reported defects, internal escapes reaching downstream processes, field failures, or any non-conformance requiring documented root cause analysis. Mandatory for most automotive OEM customer complaints (Ford 8D, BMW G8D, VW QMSS, Stellantis).

## Prerequisites

- Defect or failure clearly identified and quantified
- Access to affected parts, process records, and measurement data
- Cross-functional team availability (quality, production, engineering minimum)

## Workflow

### D0 — Emergency Response (before the team is assembled)

Ask these questions first:
1. Is this a safety or regulatory issue? If yes → escalate immediately, notify customer
2. Are suspect parts already at the customer or in the field? If yes → launch containment now (D3) before completing D1-D2
3. Capture initial evidence: photos, batch numbers, lot traceability, measurement data

D0 is complete when: safety is assessed, suspect material is identified and flagged.

---

### D1 — Team Formation

Build a cross-functional team. Required functions:
- **Champion** (sponsor, authority to release resources)
- **Team leader** (owns the 8D, drives completion)
- **Quality engineer** (methodology, documentation)
- **Production / process owner** (process knowledge)
- **Engineering** (design or process engineering)

Optional: supplier quality, logistics, customer representative.

Document: names, functions, team leader, start date, target closure date.

**Validation:** Is every affected process step represented? Does someone have authority to change the process?

---

### D2 — Problem Description

Define the problem precisely using Is/Is-Not and 5W2H. A weak D2 produces a weak D4.

**Is/Is-Not scoping (see [is-is-not-scoping](../is-is-not-scoping/) skill):**

| Question | IS | IS NOT |
|----------|----|--------|
| What is the problem? | e.g., dimensional out-of-spec | cosmetic scratch |
| What object/part? | Part number X, revision B | Part number Y |
| Where is it found? | Station 3, incoming inspection | Final test |
| When did it start? | Batch from 2026-05-12 | Earlier batches |
| How many? | 47 of 200 inspected (23.5%) | — |
| Trend? | Consistent since batch date | No spike |

**5W2H:**
- Who detected it? When? Where?
- What is the exact non-conformance (measured value vs. specification)?
- Why is it a problem (customer impact)?
- How was it detected? How many are affected?

D2 is complete when: a stranger could read it and know exactly what is wrong, on what, when, how many, and where in the supply chain.

---

### D3 — Interim Containment Actions (ICA)

ICA must **stop the non-conforming product from reaching the customer** while D4-D5 are in progress.

Typical ICAs:
- Sort / 100% inspection of suspect stock (in-process + field + customer)
- Ship-hold on all batches in the date range
- Add a specific inspection step at outgoing QC
- Customer notification and stock recovery (if product escaped)

**ICA validation — ask:**
- Does this ICA physically prevent the defect from escaping? (Yes/No — not "we will try")
- What is the evidence it is working? (inspection records, zero escapes since ICA date)
- Is it documented with an implementation date and responsible person?
- Is it temporary? (an ICA is not a permanent fix)

D3 is complete when: suspect product is contained with objective evidence, customer notified if applicable.

---

### D4 — Root Cause Analysis

Find TWO root causes:
1. **Root cause of occurrence** — why did the defect happen?
2. **Root cause of escape (detection failure)** — why was it not detected before reaching the customer/next process?

Use these tools (see referenced skills):
- [5-Why](../5why-root-cause/) for each root cause
- [Fishbone / Ishikawa](../fishbone-analysis/) for brainstorming categories
- [Is/Is-Not](../is-is-not-scoping/) to scope the problem boundaries

**Root cause validation:**
- Can you reproduce the defect by deliberately creating the root cause?
- Does removing the root cause prevent the defect in a trial run?
- Is it backed by data, not opinion?

**Reject these as final root causes:**
- "Human error" (not systemic — ask WHY the error was possible)
- "Operator didn't follow instructions" (ask WHY they didn't, or couldn't)
- "Supplier delivered bad parts" (ask WHY your incoming inspection did not catch it)

D4 is complete when: both root causes are validated with evidence.

---

### D5 — Choose Permanent Corrective Actions (PCA)

For each root cause from D4, select a permanent corrective action that:
- Directly addresses that specific root cause (not a symptom)
- Can be verified as effective
- Is feasible within the available time and resources

**Evaluation matrix (for each candidate PCA):**
- Does it address the root cause? (Yes/No)
- Can effectiveness be measured? (metric + target)
- Is it risk-free to implement? (FMEA check)
- Timeline: realistic?

Document: PCA description, responsible owner, target implementation date, verification method.

D5 is complete when: one PCA per root cause is selected and documented with verification plan.

---

### D6 — Implement and Verify Effectiveness

Implement the PCAs. After implementation:

**Verification requirements:**
- Run sufficient production volume (minimum per your statistical confidence need — typically 300 units or 30 shifts depending on defect rate)
- Measure the original defect metric before and after
- Confirm zero recurrence of the exact defect mode

**Verification evidence to capture:**
- Process control charts or inspection data after PCA
- Before/after comparison (defect rate or measurement data)
- Signed-off by quality and production

ICA (D3) can only be removed **after** D6 verification is complete with objective evidence.

D6 is complete when: data confirms the defect is eliminated, ICA formally removed.

---

### D7 — Prevent Recurrence (Systemisation)

The most valuable — and most skipped — discipline. Prevents the same root cause from appearing elsewhere.

**Required updates:**
- [ ] PFMEA updated: add/revise failure mode, update occurrence and detection ratings
- [ ] Control Plan updated: add control for root cause and escape
- [ ] Work Instructions / SOPs updated and re-issued
- [ ] Incoming inspection updated (if supplier or material related)
- [ ] Lessons learned documented and shared with similar product lines
- [ ] Training conducted for affected operators / inspectors

**Horizontal deployment:**
- Are there similar part numbers, processes, or product families that could have the same root cause?
- If yes → extend PCAs to those areas and document

D7 is complete when: all process documents are updated and changes are live in production.

---

### D8 — Team Recognition

Formally close the 8D:
- Team leader presents the completed 8D to the champion
- Champion validates all disciplines are complete with evidence
- Team is formally recognised (acknowledgement — not necessarily financial)
- 8D report is filed in the quality records system
- Closure communicated to the customer (if customer-initiated complaint)

D8 is complete when: champion signs off, customer notified of closure.

---

## Validation — is the 8D complete?

Before closing, verify:
- [ ] D2 problem description is objective and quantified
- [ ] D3 ICA has implementation date and verification evidence
- [ ] D4 has two root causes (occurrence + escape), both validated with evidence
- [ ] D5 PCAs directly address D4 root causes
- [ ] D6 verification data shows zero recurrence after PCA
- [ ] D7: FMEA, control plan, and work instructions are all updated
- [ ] D8: champion sign-off and customer notification (if applicable)

## Common mistakes

- **Skipping D0:** jumping to D2 before confirming the customer has no more suspect stock
- **Weak D2:** vague problem description leads to wrong root cause
- **D3 as D6:** treating containment as the permanent fix ("we added 100% inspection" is not a PCA)
- **Symptom as root cause:** "machine was miscalibrated" — why? "supplier sent wrong material" — why wasn't it caught?
- **Not updating D7 documents:** the most common audit finding

## Reference files

- [D0–D8 detailed guide](references/d0-d8-guide.md)
- [8D report template](assets/8d-template.md)
