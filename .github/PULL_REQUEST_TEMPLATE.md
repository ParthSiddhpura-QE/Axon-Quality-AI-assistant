## Summary

<!-- What does this PR do? New skill, correction, reference file, agent? -->

## Skill(s) affected

<!-- List each SKILL.md modified or added -->

## Standard(s) referenced

<!-- Standard name and edition for every claim in this PR -->

## Submission checklist

**Frontmatter**
- [ ] `name` matches directory name exactly
- [ ] Trigger phrases in first 400 characters of `description`
- [ ] At least 3 literal user phrases in `description`
- [ ] `description` ≤ 1024 characters
- [ ] All document control fields present (`status`, `created`, `last_updated`, `updated_by`, `reviewed_by`, `standard_edition`)

**Content**
- [ ] Content is methodology-accurate, not generic AI text
- [ ] All standard references cite specific editions and clauses
- [ ] `## Output Format` section included
- [ ] `## Changelog` section updated
- [ ] Referenced files exist on disk

**Quality gate**
- [ ] Tested with `/skill-auditor` — score ≥ 9/10

**Files staged**
- [ ] Only intended files staged (no `git add .` — explicit paths only)
