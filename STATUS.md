# STATUS — Quality-Engineering-Skills

_Last updated: 2026-06-05. Auto-updated each release._

## Summary

| Metric | Value |
|--------|-------|
| Total skills | 13 |
| Total agents | 5 |
| Reference files created | 9 |
| Skills with reference files | 9 / 13 |
| Output Format section | 18 / 18 |

**Flag legend:** 🟢 complete (output format + primary reference file present) | 🟡 partial (output format present, reference files pending) | 🔴 stub

---

## Skills

| Skill | Domain | Paired Agent | Primary Reference | Output Format | Status |
|-------|--------|--------------|-------------------|---------------|--------|
| [8d-problem-solving](skills/problem-solving/8d-problem-solving/SKILL.md) | problem-solving | 8d-coach | [d0-d8-guide.md](skills/problem-solving/8d-problem-solving/references/d0-d8-guide.md) | ✅ | 🟢 |
| [5why-root-cause](skills/problem-solving/5why-root-cause/SKILL.md) | problem-solving | rca-facilitator | [chain-validation.md](skills/problem-solving/5why-root-cause/references/chain-validation.md) | ✅ | 🟢 |
| [fishbone-analysis](skills/problem-solving/fishbone-analysis/SKILL.md) | problem-solving | — | — | ✅ | 🟡 |
| [is-is-not-scoping](skills/problem-solving/is-is-not-scoping/SKILL.md) | problem-solving | — | — | ✅ | 🟡 |
| [pdca-improvement](skills/problem-solving/pdca-improvement/SKILL.md) | problem-solving | — | — | ✅ | 🟡 |
| [pfmea-process](skills/risk-analysis/pfmea-process/SKILL.md) | risk-analysis | fmea-reviewer | [aiag-vda-2019.md](skills/risk-analysis/pfmea-process/references/aiag-vda-2019.md) | ✅ | 🟢 |
| [dfmea-design](skills/risk-analysis/dfmea-design/SKILL.md) | risk-analysis | fmea-reviewer | [interface-matrix.md](skills/risk-analysis/dfmea-design/references/interface-matrix.md) | ✅ | 🟢 |
| [action-priority-ap](skills/risk-analysis/action-priority-ap/SKILL.md) | risk-analysis | fmea-reviewer | [oem-requirements.md](skills/risk-analysis/action-priority-ap/references/oem-requirements.md) | ✅ | 🟢 |
| [ncr-writing](skills/documentation/ncr-writing/SKILL.md) | documentation | ncr-writer | [ncr-template.md](skills/documentation/ncr-writing/assets/ncr-template.md) | ✅ | 🟢 |
| [car-corrective-action](skills/documentation/car-corrective-action/SKILL.md) | documentation | — | — | ✅ | 🟡 |
| [8d-report-writing](skills/documentation/8d-report-writing/SKILL.md) | documentation | 8d-coach | [oem-formats.md](skills/documentation/8d-report-writing/references/oem-formats.md) | ✅ | 🟢 |
| [iso-9001-internal-audit](skills/audit/iso-9001-internal-audit/SKILL.md) | audit | audit-guide | [clause-questions.md](skills/audit/iso-9001-internal-audit/references/clause-questions.md) | ✅ | 🟢 |
| [iatf-16949-audit](skills/audit/iatf-16949-audit/SKILL.md) | audit | audit-guide | [supplemental-requirements.md](skills/audit/iatf-16949-audit/references/supplemental-requirements.md) | ✅ | 🟢 |

## Agents

| Agent | Skills served | Output Format | Status |
|-------|--------------|---------------|--------|
| [8d-coach](skills/agents/8d-coach/SKILL.md) | 8d-problem-solving, 8d-report-writing | ✅ | 🟢 |
| [fmea-reviewer](skills/agents/fmea-reviewer/SKILL.md) | pfmea-process, dfmea-design, action-priority-ap | ✅ | 🟢 |
| [rca-facilitator](skills/agents/rca-facilitator/SKILL.md) | 5why-root-cause | ✅ | 🟢 |
| [ncr-writer](skills/agents/ncr-writer/SKILL.md) | ncr-writing | ✅ | 🟢 |
| [audit-guide](skills/agents/audit-guide/SKILL.md) | iso-9001-internal-audit, iatf-16949-audit | ✅ | 🟢 |

---

## Pending (🟡 → 🟢)

Reference files still to create for 4 skills:

| Skill | File needed |
|-------|------------|
| fishbone-analysis | `references/6m-category-guide.md` |
| is-is-not-scoping | `references/hypothesis-elimination.md` |
| pdca-improvement | `references/pdca-examples.md` |
| car-corrective-action | `references/car-template.md` |
