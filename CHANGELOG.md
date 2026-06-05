# Changelog

All notable changes to Quality-Engineering-Skills are documented here.

---

## [v1.2.0] — 2026-06-05

### Added

**`skill-auditor` agent** — automated audit framework for SKILL.md and REFERENCE files. Scores 0–10 across 5 dimensions (Structure, Execution, Auditability, Integration, Completeness). Includes quality gates (block if score < 8), maturity model (Level 1–5), and cross-skill consistency rules. Reference: `skills/agents/skill-auditor/references/cross-skill-rules.md`.

**Governance files:**
- `CLAUDE.md` (repo) — contributor rules, structural change gates, workflow for @migmcc
- `.github/CODEOWNERS` — @RBraga01 as required reviewer on all paths
- Lead override in global `CLAUDE.md` — lead pushes directly to master; contributor uses PRs

### Changed

**Enterprise-grade polish — 10 skills** (contributed by @migmcc, PR #1):

| File | Key additions |
|------|--------------|
| `action-priority-ap/SKILL.md` | Goal, Required Checklist, M-AP clarification, revised-AP governance |
| `action-priority-ap/references/oem-requirements.md` | Required Compliance Checklist, CSR binding note, residual risk governance |
| `ncr-writing/SKILL.md` | Required NCR Checklist, legal/audit note, Critical definition expanded |
| `ncr-writing/assets/ncr-template.md` | Completion Checklist, severity escalation, effectiveness verification |
| `8d-report-writing/SKILL.md` | Required 8D Checklist, D2/D3/D4/D6 discipline improvements |
| `8d-report-writing/references/oem-formats.md` | 8D Submission Checklist, OEM rejection risks, version governance |
| `iso-9001-internal-audit/SKILL.md` | Goal, Required Audit Checklist, process-based approach, sampling guidance |
| `iso-9001-internal-audit/references/clause-questions.md` | How to use, Required Audit Behaviour, sampling rule, risk prioritisation |
| `iatf-16949-audit/SKILL.md` | Goal, Required IATF Checklist, product audit section, three-stream mandate |
| `iatf-16949-audit/references/supplemental-requirements.md` | IATF Supplemental Audit Checklist, clause-by-clause patches |

**`interface-matrix.md` audit improvements:**
- Execution checklist added at top
- Validation gate: critical interfaces must be validated by FEA/simulation/DVP
- Interface prioritisation by severity and likelihood
- Misuse and abuse scenarios in user interface section
- Direction (input/output) mandatory on all boundary diagram arrows
- Multiple interaction types must be listed explicitly (F + T + C, not collapsed)
- Statistical tolerance stack-up (RSS) when Cpk data available

**README** — GitHub usernames in Authors, expanded bios for @RBraga01 and @migmcc, badges corrected to 13 skills / 6 agents, skill-auditor added to skill index.

**LICENSE** — copyright updated to full legal name (Ricardo Romão Marques Braga).

---

## [v1.1.0] — 2026-06-05

### Added

**Output Format mechanism** — all 18 skills and agents now ask the user how they want output at invocation. Three options: Structured Markdown (A), Plain tables for Excel/Word (B), Narrative report (C). Default: A. Platform-aware: skips the question if the session context already defines a format.

**Reference files** — 9 new methodology reference files with real content (not stubs):

| File | Content |
|------|---------|
| `skills/problem-solving/8d-problem-solving/references/d0-d8-guide.md` | D0–D8 gate criteria, evidence requirements, OEM-specific notes |
| `skills/problem-solving/5why-root-cause/references/chain-validation.md` | Why chain validation rules, reversal check, anti-patterns |
| `skills/risk-analysis/pfmea-process/references/aiag-vda-2019.md` | 7-step PFMEA reference, S/O/D rating tables, PFMEA→Control Plan linkage |
| `skills/risk-analysis/dfmea-design/references/interface-matrix.md` | Interface matrix construction, boundary diagram, failure mode patterns |
| `skills/risk-analysis/action-priority-ap/references/oem-requirements.md` | OEM-specific AP requirements: Ford EJ, GM BIQS, VW, BMW, Stellantis |
| `skills/documentation/ncr-writing/assets/ncr-template.md` | Fillable NCR template with field guidance and severity decision tree |
| `skills/documentation/8d-report-writing/references/oem-formats.md` | Ford/BMW/VW/GM/Stellantis format differences and submission requirements |
| `skills/audit/iso-9001-internal-audit/references/clause-questions.md` | §4–§10 question bank with evidence anchors |
| `skills/audit/iatf-16949-audit/references/supplemental-requirements.md` | All 16 IATF supplemental requirements with audit questions |

**Observability files:**
- `STATUS.md` — skill dashboard with reference coverage, pairing, and status flags
- `CHANGELOG.md` — this file

### Changed

**Description engineering** — trigger phrases added to first 400 characters of all 18 skill descriptions. Key phrases users naturally type are now in the discoverable zone. All descriptions remain ≤1024 characters.

**CONTRIBUTING.md** — added Output Format requirement (mandatory for all new skills) and description engineering rules (trigger phrase placement, ≤1024 char limit, 3+ literal user phrases required).

---

## [v1.0.0] — 2026-06-01

### Added

Initial release.

- **13 skills** across 4 domains: problem-solving, risk-analysis, documentation, audit
- **5 interactive agents**: 8d-coach, fmea-reviewer, rca-facilitator, ncr-writer, audit-guide
- ISO 9001:2015 and IATF 16949:2016 clause mappings in all skill frontmatter
- MIT license
- Platform connector documentation: ChatGPT (GPT Actions), Claude.ai (Projects)
- CONTRIBUTING.md with skill format specification and submission checklist
