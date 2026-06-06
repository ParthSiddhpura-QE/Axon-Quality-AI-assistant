# STATUS — Quality-Engineering-Skills

_Last updated: 2026-06-06. Auto-updated each release._

## Summary

| Metric | Value |
|--------|-------|
| Total skills | 22 |
| Total agents | 8 |
| Reference files created | 10 |
| Skills with reference files | 9 / 22 |
| Output Format section | 30 / 30 |

**Flag legend:** 🟢 complete (output format + primary reference file present) | 🟡 partial (output format present, reference files pending) | 🔴 stub

---

## Skills

### Problem Solving

| Skill | Domain | Paired Agent | Primary Reference | Output Format | Status |
|-------|--------|--------------|-------------------|---------------|--------|
| [8d-problem-solving](skills/problem-solving/8d-problem-solving/SKILL.md) | problem-solving | 8d-coach | [d0-d8-guide.md](skills/problem-solving/8d-problem-solving/references/d0-d8-guide.md) | ✅ | 🟢 |
| [5why-root-cause](skills/problem-solving/5why-root-cause/SKILL.md) | problem-solving | rca-facilitator | [chain-validation.md](skills/problem-solving/5why-root-cause/references/chain-validation.md) | ✅ | 🟢 |
| [fishbone-analysis](skills/problem-solving/fishbone-analysis/SKILL.md) | problem-solving | — | — | ✅ | 🟡 |
| [is-is-not-scoping](skills/problem-solving/is-is-not-scoping/SKILL.md) | problem-solving | — | — | ✅ | 🟡 |
| [pdca-improvement](skills/problem-solving/pdca-improvement/SKILL.md) | problem-solving | — | — | ✅ | 🟡 |
| [dmaic](skills/problem-solving/dmaic/SKILL.md) | problem-solving | — | — | ✅ | 🟡 |

### Risk Analysis

| Skill | Domain | Paired Agent | Primary Reference | Output Format | Status |
|-------|--------|--------------|-------------------|---------------|--------|
| [pfmea-process](skills/risk-analysis/pfmea-process/SKILL.md) | risk-analysis | fmea-reviewer | [aiag-vda-2019.md](skills/risk-analysis/pfmea-process/references/aiag-vda-2019.md) | ✅ | 🟢 |
| [dfmea-design](skills/risk-analysis/dfmea-design/SKILL.md) | risk-analysis | fmea-reviewer | [interface-matrix.md](skills/risk-analysis/dfmea-design/references/interface-matrix.md) | ✅ | 🟢 |
| [action-priority-ap](skills/risk-analysis/action-priority-ap/SKILL.md) | risk-analysis | fmea-reviewer | [oem-requirements.md](skills/risk-analysis/action-priority-ap/references/oem-requirements.md) | ✅ | 🟢 |

### Planning

| Skill | Domain | Paired Agent | Primary Reference | Output Format | Status |
|-------|--------|--------------|-------------------|---------------|--------|
| [ppap](skills/planning/ppap/SKILL.md) | planning | ppap-checker | — | ✅ | 🟡 |
| [apqp](skills/planning/apqp/SKILL.md) | planning | — | — | ✅ | 🟡 |
| [control-plan](skills/planning/control-plan/SKILL.md) | planning | control-plan-builder | — | ✅ | 🟡 |
| [dvp-test-plan](skills/planning/dvp-test-plan/SKILL.md) | planning | — | — | ✅ | 🟡 |

### Measurement

| Skill | Domain | Paired Agent | Primary Reference | Output Format | Status |
|-------|--------|--------------|-------------------|---------------|--------|
| [msa-gauge-rr](skills/measurement/msa-gauge-rr/SKILL.md) | measurement | — | — | ✅ | 🟡 |
| [spc-control-charts](skills/measurement/spc-control-charts/SKILL.md) | measurement | — | — | ✅ | 🟡 |

### Documentation

| Skill | Domain | Paired Agent | Primary Reference | Output Format | Status |
|-------|--------|--------------|-------------------|---------------|--------|
| [ncr-writing](skills/documentation/ncr-writing/SKILL.md) | documentation | ncr-writer | [ncr-template.md](skills/documentation/ncr-writing/assets/ncr-template.md) | ✅ | 🟢 |
| [car-corrective-action](skills/documentation/car-corrective-action/SKILL.md) | documentation | — | — | ✅ | 🟡 |
| [8d-report-writing](skills/documentation/8d-report-writing/SKILL.md) | documentation | 8d-coach | [oem-formats.md](skills/documentation/8d-report-writing/references/oem-formats.md) | ✅ | 🟢 |

### Audit

| Skill | Domain | Paired Agent | Primary Reference | Output Format | Status |
|-------|--------|--------------|-------------------|---------------|--------|
| [iso-9001-internal-audit](skills/audit/iso-9001-internal-audit/SKILL.md) | audit | audit-guide | [clause-questions.md](skills/audit/iso-9001-internal-audit/references/clause-questions.md) | ✅ | 🟢 |
| [iatf-16949-audit](skills/audit/iatf-16949-audit/SKILL.md) | audit | audit-guide | [supplemental-requirements.md](skills/audit/iatf-16949-audit/references/supplemental-requirements.md) | ✅ | 🟢 |
| [vda-6-3-audit](skills/audit/vda-6-3-audit/SKILL.md) | audit | — | — | ✅ | 🟡 |

### Supplier Quality

| Skill | Domain | Paired Agent | Primary Reference | Output Format | Status |
|-------|--------|--------------|-------------------|---------------|--------|
| [supplier-scar](skills/supplier-quality/supplier-scar/SKILL.md) | supplier-quality | — | — | ✅ | 🟡 |

---

## Agents

| Agent | Skills served | Output Format | Status |
|-------|--------------|---------------|--------|
| [8d-coach](skills/agents/8d-coach/SKILL.md) | 8d-problem-solving, 8d-report-writing | ✅ | 🟢 |
| [fmea-reviewer](skills/agents/fmea-reviewer/SKILL.md) | pfmea-process, dfmea-design, action-priority-ap | ✅ | 🟢 |
| [rca-facilitator](skills/agents/rca-facilitator/SKILL.md) | 5why-root-cause | ✅ | 🟢 |
| [ncr-writer](skills/agents/ncr-writer/SKILL.md) | ncr-writing | ✅ | 🟢 |
| [audit-guide](skills/agents/audit-guide/SKILL.md) | iso-9001-internal-audit, iatf-16949-audit | ✅ | 🟢 |
| [skill-auditor](skills/agents/skill-auditor/SKILL.md) | all skills (framework audit) | ✅ | 🟢 |
| [ppap-checker](skills/agents/ppap-checker/SKILL.md) | ppap | ✅ | 🟢 |
| [control-plan-builder](skills/agents/control-plan-builder/SKILL.md) | control-plan | ✅ | 🟢 |

---

## Pending

### Review gate (blocking Week 5 launch)

| Item | Owner | Status |
|------|-------|--------|
| migmcc methodology review of 11 new SKILL.md files (9 skills + 2 agents) | @migmcc | ⏳ pending |
| Review brief `docs/review-brief-migmcc-v2.md` sent | @RBraga01 | ✅ done |
| Skill-auditor gate: all 11 files must score ≥ 9/10 before PR opens | @migmcc | ⏳ pending |
| PR `review/v2-new-skills` merged | @RBraga01 | ⏳ pending |

### Reference files (🟡 → 🟢) — 13 skills pending

| Skill | File needed |
|-------|------------|
| fishbone-analysis | `references/6m-category-guide.md` |
| is-is-not-scoping | `references/hypothesis-elimination.md` |
| pdca-improvement | `references/pdca-examples.md` |
| car-corrective-action | `references/car-template.md` |
| dmaic | `references/statistical-tools.md` |
| ppap | `references/18-elements-checklist.md` |
| apqp | `references/phase-deliverables.md` |
| control-plan | `references/control-plan-template.md` |
| dvp-test-plan | `references/dvp-template.md` |
| msa-gauge-rr | `references/gauge-rr-study-guide.md` |
| spc-control-charts | `references/chart-selection-guide.md` |
| vda-6-3-audit | `references/p1-p7-questions.md` |
| supplier-scar | `references/scar-template.md` |

### Week 5 — blocked until migmcc review PR merged

- [ ] Web app PWA
- [ ] Public API endpoint
- [ ] Demos / GIFs for README
- [ ] agentskills.io registry submission
- [ ] Repo goes PUBLIC
- [ ] Store submission URLs live (privacy policy, AppSource, Marketplace, Slack App Directory)
