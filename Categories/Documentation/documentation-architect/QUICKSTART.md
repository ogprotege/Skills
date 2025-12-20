# Documentation Architect — Quick Start

This guide shows how to safely and effectively use the **Documentation Architect** for day-to-day documentation work.

---

## What This Tool Is Best At

Use **documentation-architect** when you want to:
- Improve or update documentation for a specific area
- Clean up, reorganize, or clarify existing docs
- Fix documentation drift after code changes
- Add missing documentation without rewriting everything
- Maintain documentation quality over time

This tool works best **incrementally**, not repo-wide.

---

## 1. Always Start With a Clear Scope

You must tell the agent *exactly* where to look.

Good scopes:
- A service or feature  
  `/services/auth`
- A documentation subtree  
  `/docs/api`
- A single document  
  `/docs/architecture/auth.md`

Avoid vague scopes like “the repo” unless you truly mean it.

---

## 2. Start in Plan Mode (Recommended)

Plan mode lets the agent analyze and propose changes without modifying anything.

Example:
Use documentation-architect
Scope: /services/auth and /docs/auth
Mode: plan
Debug: on
Goal: Identify outdated auth documentation and propose improvements

What you’ll get:
- Context Snapshot (what it read and understood)
- Inventory of docs in scope
- Drift findings (docs vs code mismatches)
- Proposed reorganization or edits
- No files changed

---

## 3. Review the Context Snapshot First

Before approving anything, confirm:
- The agent read the correct files
- Its understanding of the system is accurate
- No important areas were missed

If the snapshot is wrong, **stop and correct the scope**.

---

## 4. Review Proposed Changes

In plan mode, the agent will propose:
- Which docs are active, deprecated, or archived
- What needs to be updated or clarified
- Any suggested file moves or cross-links
- Review scheduling recommendations

If something feels too aggressive, say so. The agent is designed to adjust.

---

## 5. Apply Changes Only When Ready

When you’re satisfied:

Mode: apply

The agent will:
- Execute the approved plan
- Update documentation files
- Produce a concise change summary

For large scopes, apply changes in batches.

---

## 6. Use Debug Mode When Stakes Are High

Enable debug mode when:
- The system is complex
- Docs are safety-critical
- You’re unsure about drift findings

Debug mode explains:
- Why decisions were made
- What evidence was used
- How changes can be rolled back

---

## Common Mistakes to Avoid

- Running without a scope
- Skipping plan mode on first use
- Letting it operate repo-wide unintentionally
- Treating it like a one-shot doc generator
- Applying large changes without review

---

## Mental Model

Think of **documentation-architect** as:
- A careful maintainer
- A documentation reviewer with context
- A long-term quality steward

You remain in control.  
The tool proposes; you approve.

---

## When Not to Use This Tool

- When you want a full documentation rewrite from scratch  
  (use a repo-wide audit tool instead)
- When you don’t yet understand the code yourself
- When quick, throwaway docs are sufficient

---

## Final Tip

Small, focused runs produce the best results.

Treat documentation as something you *maintain*, not something you “finish,” and this tool will pay for itself very quickly.