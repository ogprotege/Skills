# Documentation Skills — Commands Cheat Sheet

This cheat sheet provides safe, common command patterns for documentation maintenance and auditing.

Use these as starting points. Always adjust the scope intentionally.

---

## documentation-architect

Use for **incremental, scoped documentation maintenance**.

### Verify docs after a code change (weekly)

```text
Use documentation-architect
Scope: /services/auth
Mode: plan
Goal: Verify documentation matches recent auth changes
```

---

### Clean up a docs subtree (monthly)

```text
Use documentation-architect
Scope: /docs/api
Mode: plan
Debug: on
Goal: Identify outdated or duplicated API documentation
```

---

### Apply approved documentation updates

```text
Use documentation-architect
Scope: /docs/runbooks
Mode: plan
Goal: Improve structure and cross-linking without changing meaning
```

---

### Reorganize docs without rewriting content

```text
Use documentation-architect
Scope: /docs/runbooks
Mode: plan
Goal: Improve structure and cross-linking without changing meaning
```

---

---

## repo-doc-auditor

Use for deep, evidence-based documentation audits and rebuild proposals.

### Full documentation audit (plan-only)

```text
Use repo-doc-auditor
Scope: entire repo
Mode: plan
Debug: on
Goal: Audit documentation accuracy and propose a clean replacement set
```

---

### Pre-release documentation validation

```text
Use repo-doc-auditor
Scope: entire repo
Target branch: release/v2
Mode: plan + generate
Goal: Validate documentation for upcoming release
```

---

### Generate review-only documentation set

```text
Use repo-doc-auditor
Scope: /services/auth, /docs/auth
Mode: generate
Goal: Create review-only documentation for auth subsystem
```

---

## Safety Notes
- Always start in plan mode
- Repo-wide scope must be intentional
- Generated documentation is never merged automatically
- When in doubt, enable debug mode

---

## Choosing the Right Tool
- Small fixes, reorganization, ongoing hygiene → documentation-architect
- Accuracy audits, large refactors, release prep → repo-doc-auditor

---