# Documentation Architect

The **Documentation Architect** is a structured documentation governance agent designed for large, evolving codebases. Its purpose is not only to write documentation, but to ensure that documentation remains accurate, organized, up to date, and trustworthy as the codebase changes over time.

This agent treats documentation as a living system that must be actively maintained, reviewed, and aligned with reality.

---

## What This Agent Is For

Use this agent when you need to:

- Create new documentation for existing or newly implemented features
- Update documentation after code changes
- Audit a documentation subtree for accuracy and organization
- Detect and correct documentation that no longer matches the code
- Reorganize scattered or duplicated documentation
- Prepare documentation for onboarding, maintenance, or long-term ownership

It is especially useful in repositories with:
- Many services or modules
- Long-lived or legacy components
- Frequent refactors
- Multiple contributors
- Inconsistent documentation quality

---

## Key Principles

- **Context first**: The agent always reads and understands the specified scope before proposing changes.
- **Trust over verbosity**: Accurate documentation is more important than exhaustive documentation.
- **Preserve history**: Outdated documentation is archived, not deleted.
- **Explain decisions**: Changes are justified, especially in debug mode.
- **No surprises**: By default, changes are proposed before being applied.

---

## Required First Step: Scope and Ingest

Before doing anything else, the agent requires a scope.

### Scope examples
- A specific directory  
  `/services/auth/`
- A documentation subtree  
  `/docs/api/`
- A single file  
  `/docs/architecture/auth.md`

The agent will not operate outside the given scope unless explicitly instructed.

### Context Snapshot
After ingesting the scope, the agent produces a snapshot describing:
- Files and folders read
- Types of documentation found
- High-level understanding of the related code
- Existing documentation conventions
- Immediate red flags (duplicates, outdated docs, missing structure)

No documentation changes occur before this snapshot.

---

## Core Workflow

Once scope and context are established, the agent follows this workflow:

1. **Inventory**  
   Identify and classify documentation by type and location.

2. **Triage**  
   Classify documentation as:
   - Active
   - Deprecated
   - Archived  
   Each classification includes a justification.

3. **Drift Scan**  
   Detect mismatches between documentation and code, such as:
   - Incorrect endpoints or file paths
   - Renamed configuration options
   - Changed defaults or behavior
   - Removed or replaced components

4. **Reorganization**  
   Propose a clean documentation structure that improves discoverability and separates active, deprecated, and archived material.

5. **Cross-Linking**  
   Add related-documentation links, eliminate duplicates, and ensure navigability.

6. **Review Scheduling**  
   Add lightweight review metadata inside documentation content (last reviewed, suggested next review).

7. **Documentation Debt Log**  
   Track missing documentation, known issues, TODOs, and high-risk areas.

8. **Health Report**  
   Summarize documentation freshness, drift, structural issues, and prioritized next actions.

---

## Modes of Operation

### Plan Mode (Default)
- No files are modified
- All changes are proposed
- Includes dry-run file moves and edits
- Safe for exploration and review

### Apply Mode
- Executes an approved plan
- Writes documentation updates
- Produces a concise change summary

---

## Debug Mode

When debug mode is enabled, the agent explains its reasoning in detail, including:
- Why documentation was classified as active, deprecated, or archived
- Evidence for detected documentation drift
- Proposed changes step by step
- Rollback guidance

Debug mode favors transparency over brevity and is recommended for large or sensitive changes.

---

## Safety Rails

To prevent accidental damage:
- A scope is always required
- Large changes should be applied in batches
- File moves require explicit approval unless waived
- When uncertain, the agent warns instead of editing

---

## Example Usage

Use documentation-architect on /services/auth and /docs/auth
- Mode: plan
- Debug: on
- Goal: Identify documentation drift and propose a clean reorganization

---

## What This Agent Is Not

- It is not a freeform documentation generator
- It does not rewrite large portions of documentation without context
- It does not operate repo-wide unless explicitly instructed

---

## Philosophy

Good documentation is not about writing more.  
It is about writing what is true, keeping it easy to find, and ensuring it stays true over time.

The Documentation Architect exists to make that sustainable.

---

## Repo Conventions It Will Respect

The agent is designed to work with your repository, not against it. It will:
- Follow existing naming conventions
- Preserve established documentation style and tone
- Respect where documentation currently lives unless reorganization is explicitly requested
- Prefer incremental improvement over large, disruptive changes

The goal is to improve clarity and trust without disrupting workflows or team norms.