# Repo Documentation Auditor — Quick Start

This guide shows how to safely use the Repo Documentation Auditor without surprises.

---

## 1. Decide Your Scope

Be explicit. Smaller scopes are safer.

Examples:
- A service:
  /services/auth
- A docs subtree:
  /docs/api
- Entire repo (must be explicit):
  entire repository

---

## 2. Start in Plan + Debug Mode (Recommended)

This is the safest way to begin.

Example:

Use repo-doc-auditor  
Scope: /services/auth  
Target branch: main  
Mode: plan + debug  
Goal: Identify documentation drift and propose a corrected doc set

What you get:
- Context Snapshot
- Documentation inventory
- Drift findings with evidence
- Proposed documentation structure
- No files written

---

## 3. Review the Proposed Plan

Before anything is generated, review:
- What files will be created
- Folder structure under TempDoc-ForUserReview/
- Assumptions or open questions
- Areas marked “needs confirmation”

If something looks off, correct the assumptions first.

---

## 4. Generate Review-Only Documentation

Once satisfied with the plan:

Mode: generate

The agent will:
- Create TempDoc-ForUserReview/
- Write proposed documentation only
- Leave existing docs untouched

---

## 5. Review Using Git

Compare old vs new docs safely:

git diff --no-index docs/ TempDoc-ForUserReview/docs/

Or review section by section.

---

## 6. Use the Approval Checklist

Before merging anything:
- Verify technical accuracy
- Confirm naming and conventions
- Resolve open questions
- Ensure sensitive details are correct

Do not skip this step.

---

## 7. Apply Changes (Optional, Never Required)

Only after approval:

Mode: apply

Recommended approach:
- Merge incrementally
- Start with README and core docs
- Leave legacy or low-confidence areas for later

---

## Common Mistakes to Avoid

- Running repo-wide without a plan
- Skipping debug mode on first run
- Assuming generated docs are automatically correct
- Applying everything in one batch
- Treating this as a “doc generator” instead of an audit partner

---

## Mental Model

Think of this agent as:
- A meticulous reviewer
- A second set of expert eyes
- A documentation reconstruction proposal

You stay in control at every step.