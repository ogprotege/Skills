# Repo Documentation Auditor — SKILL.md Validation Checklist

Use this checklist to ensure the SKILL definition is valid, loadable, and safe to run.

---

## Frontmatter Validation

- [ ] Only allowed top-level keys are present:
      - name
      - description
      - license (optional)
      - allowed-tools (optional)
      - compatibility (optional)
      - metadata
- [ ] description is:
      - Plain text only (no XML/HTML tags)
      - Under 1024 characters
      - Free of examples, code blocks, or structured markup
- [ ] metadata contains only scalar values (string → string)
- [ ] YAML parses cleanly with no warnings or implicit types
- [ ] No arrays or nested objects in frontmatter

---

## Behavioral Guarantees

- [ ] The skill explicitly requires a scope before operating
- [ ] Repo-wide operation requires explicit user instruction
- [ ] Existing documentation is never overwritten by default
- [ ] All generated output is written to TempDoc-ForUserReview/
- [ ] Apply behavior is gated behind explicit user approval
- [ ] Plan / Generate / Apply modes are clearly distinguished

---

## Safety and Trust Checks

- [ ] Evidence-based claims are required and stated
- [ ] Assumptions are clearly labeled as such
- [ ] Unknowns trigger questions, not guesses
- [ ] Debug mode explains decisions and evidence
- [ ] Large repos are handled in stages or subsystems

---

## Output Integrity

- [ ] Generated docs are internally consistent
- [ ] Cross-links are correct within TempDoc-ForUserReview/
- [ ] No references to files that do not exist in the repo
- [ ] No sensitive or proprietary assumptions are invented
- [ ] File naming and structure are intentional and explained

---

## Operator Experience

- [ ] Context Snapshot is produced before any writing
- [ ] Proposed documentation plan is shown before generation
- [ ] Review Package includes:
      - Summary of changes
      - Key improvements
      - Open questions
      - Suggested merge strategy
- [ ] Rollback guidance is included for Apply mode

---

## Final Sanity Check

- [ ] A senior engineer could read this skill and trust it
- [ ] A maintainer could safely say “yes, run this”
- [ ] The skill improves documentation quality without forcing adoption

If all boxes are checked, the SKILL.md is valid and production-ready.
