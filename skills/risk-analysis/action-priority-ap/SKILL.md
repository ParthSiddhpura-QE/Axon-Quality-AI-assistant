---
name: action-priority-ap
description: >-
  Assign AP table ratings (H-AP, M-AP, L-AP) in PFMEA or DFMEA — the RPN replacement from
  AIAG-VDA FMEA Handbook 2019. Explains H/M/L classification logic, mandatory action
  requirements for High Priority items, and OEM-specific thresholds. Use when assigning risk
  levels in PFMEA or DFMEA, or auditing FMEA documents for AP compliance.
license: MIT
metadata:
  author: RBraga01
  version: "1.0"
  iatf-16949: "8.3.3.3"
  aiag-reference: "AIAG-VDA FMEA Handbook 2019, Step 5, Table 5-3"
  domain: quality-engineering
  subdomain: risk-analysis
  industries: automotive,electronics,aerospace,medical,general
---

# Action Priority (AP) — AIAG-VDA 2019

## Why AP replaces RPN

The legacy **RPN = Severity × Occurrence × Detection** had critical flaws:

**Problem 1 — Same RPN, very different risk**
- S=6, O=6, D=6 → RPN = 216
- S=9, O=8, D=3 → RPN = 216
The second scenario involves a safety-related severity (S=9) and high occurrence — far more dangerous — yet produces the same RPN.

**Problem 2 — Easy to game**
Teams learned to lower RPN cheaply by improving detection (adding an inspection step). D: 8→3 drops RPN by 62.5%. But the defect is still being made — it's just being caught later. Prevention (reducing occurrence) is harder but far more valuable.

**Problem 3 — No mandatory threshold**
RPN had no defined threshold for mandatory action. "High RPN" meant different things to different teams and customers.

**The AP fix:**
- S=9 or S=10 → **always H** (mandatory action), regardless of O and D
- AP looks at S and O together first (risk of harm occurring), then considers D
- Requires documented action or documented rationale for no action

---

## AP Classification

### H — High Priority

**Action required.** Assign a responsible person and a target completion date.

If no improvement is achievable (technically or economically), the team must:
1. Document why no action is possible
2. Escalate to management for acceptance of residual risk
3. Get management sign-off

H-AP items must never be silently ignored.

**Conditions that always produce H:**
- S = 9 or 10 (any O, any D)
- S = 8 + O = 6–10 + D = 6–10

### M — Medium Priority

**Action recommended.** The team should evaluate whether risk reduction is beneficial.

Document the evaluation decision:
- Action taken → describe the action
- No action → document why (risk accepted, cost-prohibitive, technically infeasible)

### L — Low Priority

**No action required.** Document rationale for the record.

---

## AP Assessment Workflow

For each FC (Failure Cause) row in the PFMEA/DFMEA:

```
1. Assign S (for the linked Failure Effect)
2. Is S = 9 or 10?
   → Yes: AP = H. Done.
   → No: continue

3. Assign O (for this Failure Cause with current prevention controls)
4. Assign D (for this Failure Mode with current detection controls)
5. Look up AP in the table (see assets/ap-table.md for full table)
```

---

## Action priority by S bracket

### S = 9–10 (Safety / Regulatory)

| O | D | AP |
|---|---|----|
| Any | Any | **H** |

### S = 8 (Loss of primary function)

| O | D | AP |
|---|---|----|
| 6–10 | Any | **H** |
| 4–5 | 6–10 | **H** |
| 4–5 | 1–5 | **M** |
| 1–3 | Any | **M** |

### S = 7 (Reduced primary function)

| O | D | AP |
|---|---|----|
| 6–10 | 7–10 | **H** |
| 6–10 | 4–6 | **M** |
| 6–10 | 1–3 | **M** |
| 4–5 | 7–10 | **M** |
| 4–5 | 4–6 | **M** |
| 4–5 | 1–3 | **L** |
| 1–3 | Any | **L** |

### S = 6 (Loss of comfort/convenience)

| O | D | AP |
|---|---|----|
| 8–10 | 7–10 | **H** |
| 8–10 | 4–6 | **M** |
| 8–10 | 1–3 | **M** |
| 5–7 | 7–10 | **M** |
| 5–7 | 1–6 | **L** |
| 1–4 | Any | **L** |

### S = 1–5

All combinations → **L**

---

## Reviewing an existing FMEA for AP compliance

Audit questions:
1. Are all S=9/10 rows assigned AP=H?
2. Do all H-AP rows have an assigned owner AND target date?
3. Are there any H-AP rows with no action and no documented escalation rationale?
4. For rows where AP was improved (revised AP column): is the action implemented and verified?
5. Are Special Characteristics all rated S=9 or S=10?

---

## Customer-specific notes

| OEM | AP requirement |
|-----|---------------|
| Ford | H-AP items require mandatory action or documented engineering justification (EJ) |
| GM | BIQS requires all H-AP items closed before PPAP Level 3 |
| VW/Audi | AP H must be actioned or formally accepted by responsible engineer |
| BMW | AP H items listed on open issues list until closed |
| Stellantis | H-AP items require SQE approval for acceptance without action |

Always check the customer's current CSR (Customer-Specific Requirements) — these override general guidance.

## Output Format

At the start of each use, ask the user:

> "How would you like to receive the output?
> **A** — Structured Markdown (formatted tables and sections, ready to copy)
> **B** — Plain tables (simplified structure for Excel or Word)
> **C** — Narrative report (flowing text for a formal document or email)
>
> Default: A."

Adapt all output sections to the chosen format. If the platform or session context already defines a format preference, skip this question.
