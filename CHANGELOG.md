# Changelog

All notable changes to Quality-Engineering-Skills are documented here.

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
