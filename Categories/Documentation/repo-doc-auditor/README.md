# Repo Documentation Auditor

The **Repo Documentation Auditor** is a high-precision documentation audit and reconstruction agent designed for large, complex repositories. It reads code, recent changes, and existing documentation, then produces a **fully proposed, technically accurate documentation set** for user review—without touching your current docs.

Think of it as a collaboration with a codebase-savvy documentation expert that verifies everything before writing anything.

---

## What This Agent Does

The Repo Documentation Auditor performs a **repo-wide, evidence-based audit** of documentation against the actual codebase and recent changes (commits, PRs, releases). It then generates a **complete, corrected documentation set** inside a review-only folder:

TempDoc-ForUserReview/

Nothing is overwritten. Nothing is deleted.  
All changes are proposed, explained, and gated behind explicit user approval.

---

## When to Use This Agent

Use this agent when you want to:

- Audit documentation for accuracy against the current codebase
- Catch silent documentation drift after refactors or feature growth
- Rebuild README, API, CLI, and technical docs from first principles
- Prepare documentation for a major release or handoff
- Compare your existing docs against a clean “ground truth” rewrite
- Collaborate with an agent that treats correctness as non-negotiable

This agent is ideal for:
- Proprietary repositories
- Long-lived or legacy systems
- Large monorepos
- Rapidly evolving APIs or CLIs
- Teams that care about documentation quality and trust

---

## Core Guarantees

- **Read first, write later**  
  The agent ingests and understands context before proposing changes.

- **Evidence-based**  
  Every documentation claim is traceable to code, configuration, tests, or commit history.

- **Non-destructive**  
  All output is written to `TempDoc-ForUserReview/` only.

- **Approval-gated**  
  Nothing is applied to existing documentation without explicit user consent.

- **Transparent reasoning**  
  Debug mode explains every decision.

---

## Required First Step: Scope and Context

The agent always operates within a defined scope.

### Example scopes
- Entire repository
- A specific service or module
- A documentation subtree
- A release branch or tag

The agent will not operate repo-wide unless explicitly instructed.

---

## High-Level Workflow

1. **Scope + Ingest**  
   Read the specified files, folders, or entire repo.

2. **Context Snapshot**  
   Summarize:
   - Repo structure and technologies
   - Existing documentation layout
   - Tooling and interfaces (API, CLI, config)
   - Immediate risks and gaps

3. **Change Awareness**  
   Review recent commits and PRs to understand what likely changed.

4. **Documentation Inventory**  
   Map all existing documentation and classify its purpose and status.

5. **Drift Scan**  
   Compare documentation claims to actual code and configuration.

6. **Proposed Documentation Plan**  
   Present a file-by-file plan and structure before writing anything.

7. **Generate Review-Only Docs**  
   Create a full proposed documentation set in `TempDoc-ForUserReview/`.

8. **Review Package**  
   Provide summaries, diffs, open questions, and a suggested merge strategy.

---

## What Gets Generated

Depending on the repository, the agent may generate:

- `README.md`
- `CHANGELOG.md`
- Architecture and system overview documents
- API documentation and examples
- CLI documentation and workflows
- Configuration references
- Development, testing, and deployment guides
- Runbooks and troubleshooting guides
- Technical specifications

All generated content is internally consistent, cross-linked, and clearly structured.

---

## Example `TempDoc-ForUserReview/` Structure

TempDoc-ForUserReview/
├── README.md
├── CHANGELOG.md
├── docs/
│   ├── overview.md
│   ├── architecture/
│   │   ├── system.md
│   │   └── data-flow.md
│   ├── api/
│   │   ├── overview.md
│   │   └── endpoints.md
│   ├── cli/
│   │   └── commands.md
│   ├── configuration/
│   │   └── options.md
│   ├── development/
│   │   ├── setup.md
│   │   └── testing.md
│   ├── deployment/
│   │   └── release-process.md
│   ├── runbooks/
│   │   └── operations.md
│   └── troubleshooting/
│       └── common-issues.md

This folder is review-only and is never merged automatically.

---

## Modes of Operation

### Plan Mode (Default)
- No files are written
- Outputs a proposed documentation plan
- Safe for exploration and review

### Generate Mode
- Writes proposed documentation into `TempDoc-ForUserReview/`
- Still does not modify existing docs

### Apply Mode (Optional, Never Default)
- Requires explicit approval
- Proposes exact replacements or merges
- Includes rollback guidance

---

## Debug Mode

When debug mode is enabled, the agent will:
- Explain why documentation is considered stale or incorrect
- Show evidence for detected drift
- Log reasoning step by step
- Clearly mark assumptions and unknowns

Debug mode is recommended for large or sensitive repositories.

---

## Reviewing Changes: Plain Git Workflow

A typical review flow looks like this:

- git checkout -b doc-audit-review
- diff -ru docs/ TempDoc-ForUserReview/docs/

Or, for selective comparison:

- git diff –no-index docs/api TempDoc-ForUserReview/docs/api

You can then manually copy, merge, or cherry-pick approved files into your main documentation tree.

---

## Documentation Approval Checklist

Before applying any generated documentation, confirm:

- [ ] All claims are supported by code, configuration, or tests
- [ ] API and CLI examples match current behavior
- [ ] No outdated concepts or removed features are referenced
- [ ] Terminology matches repo conventions
- [ ] Sensitive or proprietary details are correct and appropriate
- [ ] File placement aligns with existing repo structure
- [ ] Open questions or assumptions have been resolved
- [ ] A rollback path is understood

Only after this checklist is satisfied should documentation be merged.

---

## Safety Rails

- Scope is mandatory
- Repo-wide audits must be explicit
- Existing docs are never overwritten automatically
- Large repos are handled in stages when necessary
- When uncertain, the agent asks questions instead of guessing

---

## Example Usage

```text
Use repo-doc-auditor
Scope: entire repo
Target branch: main
Mode: plan + debug
Goal: Perform a full documentation audit and propose a complete replacement set for review

---

## What This Agent Is Not

- It is not a freeform documentation generator
- It does not guess or invent behavior
- It does not silently rewrite your docs
- It does not operate without user direction

---

## Philosophy

## Documentation should represent truth, not intention.

## The Repo Documentation Auditor exists to:

- Make documentation accurate
- Make structure obvious
- Preserve history without confusion
- Give maintainers confidence in what they ship

It treats documentation as a system that deserves the same rigor as code.

---

## Optional Next-Level Enhancements

## If deeper polish or tighter collaboration is desired, this agent can be extended with:

- A sample TempDoc-ForUserReview/ directory tree tailored to your repo
- A more detailed comparison workflow for large-scale diffs
- Automated approval checklists or validation reports
- Additional output formats for long-term documentation governance

These enhancements are optional. The agent is intentionally designed to be powerful, safe, and complete without them.

---