# Documentation Maintenance Cadence Guide

This guide defines a lightweight, repeatable rhythm for keeping documentation accurate, organized, and trustworthy over time.

The goal is **preventing documentation decay**, not creating busywork.

---

## Core Principle

Documentation should be maintained like code:
- Small, regular updates
- Clear ownership
- Periodic audits
- No large, painful rewrites unless unavoidable

---

## Weekly Maintenance (10–30 minutes)

**Purpose:** Catch drift early and keep active docs reliable.

### What to Do
- Review documentation related to:
  - Code you touched this week
  - Merged PRs
  - Recent bug fixes or behavior changes
- Update:
  - Examples that no longer match code
  - Command outputs, flags, or config defaults
  - Small clarifications where confusion arose

### Recommended Tool
Use `documentation-architect` with a **narrow scope**.

Example:
Scope: /services/auth
Mode: plan
Goal: Verify auth docs still match this week’s changes

### Checklist
- [ ] Docs still reflect current behavior
- [ ] No references to removed files or features
- [ ] Examples still make sense
- [ ] No TODOs added without context

---

## Monthly Maintenance (1–2 hours)

**Purpose:** Structural health and clarity.

### What to Do
- Review a documentation subtree:
  - `/docs/api`
  - `/docs/architecture`
  - `/docs/runbooks`
- Look for:
  - Duplicate docs
  - Docs that should be deprecated or archived
  - Missing cross-links
  - Naming or placement inconsistencies

### Recommended Tool
Use `documentation-architect` in **plan mode**, optionally with debug.

Example:
Scope: /docs/api
Mode: plan
Debug: on
Goal: Clean up API docs and improve discoverability

### Checklist
- [ ] Active vs deprecated docs are clearly separated
- [ ] Cross-links exist where helpful
- [ ] Folder structure still makes sense
- [ ] Review dates are reasonable
- [ ] High-traffic docs are easy to find

---

## Quarterly Maintenance (Half day)

**Purpose:** Accuracy, trust, and onboarding quality.

### What to Do
- Review:
  - Root README
  - Architecture overview
  - Onboarding or setup docs
- Validate:
  - Mental model is still correct
  - Setup steps still work
  - Dependencies and tooling are current

### Recommended Tool
Use `documentation-architect` or `repo-doc-auditor` on **focused scope**, not the entire repo unless necessary.

Example:

Scope: README.md, /docs/architecture
Mode: plan
Goal: Ensure high-level docs still reflect system reality

### Checklist
- [ ] README accurately describes the system
- [ ] Architecture diagrams still match reality
- [ ] New contributors could get started without tribal knowledge
- [ ] Outdated concepts are archived, not deleted

---

## Pre-Release Maintenance (As Needed)

**Purpose:** Ship documentation with confidence.

### What to Do
- Verify:
  - CHANGELOG entries
  - API/CLI docs for released features
  - Breaking changes are clearly documented
- Ensure:
  - Migration paths are documented
  - Deprecated features are clearly labeled

### Recommended Tool
Use `repo-doc-auditor` in **plan + generate mode**.

Example:
Scope: entire repo
Target branch: release/v2
Mode: plan + debug
Goal: Validate documentation for upcoming release

### Checklist
- [ ] Docs match the release branch
- [ ] Breaking changes are visible
- [ ] No stale references to removed features
- [ ] Review-only docs generated before merging

---

## Annual Maintenance (Optional but Powerful)

**Purpose:** Reset accumulated documentation debt.

### What to Do
- Perform a repo-wide documentation audit
- Generate a full review set in `TempDoc-ForUserReview/`
- Compare current docs against a clean, evidence-based rewrite

### Recommended Tool
Use `repo-doc-auditor`.

Example:
Scope: entire repo
Mode: plan
Debug: on
Goal: Full documentation health audit

### Outcome
- Clear picture of doc health
- Prioritized cleanup plan
- No rushed or risky changes

---

## Signals It’s Time to Run Maintenance Early

Run maintenance outside the schedule if:
- Engineers stop trusting docs
- Questions repeat in Slack or issues
- New hires struggle to onboard
- Refactors land without doc updates
- You hear “the docs are probably wrong”

---

## Mental Model

- **Weekly:** correctness
- **Monthly:** organization
- **Quarterly:** understanding
- **Pre-release:** confidence
- **Annual:** reset

Small, regular attention prevents big documentation failures.

Good documentation doesn’t happen all at once.  
It stays good because someone is paying attention.