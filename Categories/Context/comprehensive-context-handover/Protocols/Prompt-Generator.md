# CCHP v2.1: GENERATOR PROMPT (REVIEWED + FIXED)

**Instructions**: Copy and paste the text below into the chat when you are ready to initiate a forensic context handover.

Execute the **comprehensive-context-handover** skill (CCHP v2.1).

Analyze the entirety of our conversation history with forensic precision. Do not “summarize.” Reconstruct. Your goal is to preserve the **trajectory of thought** for a cold-start resumption in a new session.

## Hard Rules (Non-Negotiable)


Output Requirements:
- **Produce the final artifact as a downloadable Markdown (.md) file.**
- **The filename must be explicit and stable (e.g., CONTEXT_TRANSFER_<subject>_<date(mm/dd/yy/)>.md).**
- **Do not provide alternative formats or inline-only substitutes.**
- **No truncation by judgment**: Do not omit anything because it seems minor.
- **Preserve load-bearing wording**: Keep exact phrasing for “must / never / only” constraints.
- **Fact vs meaning separation**: Facts are what was said/decided; meaning explains why it matters.
- **Domain-agnostic by default**: Do not pre-assume a domain. Detect it from the conversation.
- **Not for code continuation unless explicit**: Only include code/file details if the chat explicitly requires code continuation.
- **Use the Canonical Artifact Template v2.1 exactly**: Do not rename sections, reorder sections, or omit sections. If a section does not apply, write **N/A**.
- **If token limits threaten truncation**: Preserve sections in this order:
  1) § 1 IMMEDIATE ORIENTATION
  2) § 2 USER NON-NEGOTIABLES
  3) § 3 DECISION LOG
  4) § 4 REQUIREMENTS LEDGER
  5) § 7 OPEN LOOPS
  6) § 6 CRITICAL CONTEXT & INSIGHT EVOLUTION
  7) § 5 ARTIFACTS & OUTPUTS
  8) § 8 CONVERSATION HISTORY
  9) § 9 TRANSFER METADATA
  10) § 10 RESUMPTION HANDSHAKE

## Core Extraction Requirements

1) **Immediate Orientation**
- Define the mission and underlying why.
- State current status and momentum.
- Provide the single “Next Action” (chunk protocol).
- Include 3–10 “Stop Re-Asking” points.

2) **User Non-Negotiables**
- Capture formatting constraints, scope constraints, behavior/tone constraints.
- Preserve hard rules verbatim when possible.

3) **Decision Log (Anti-Rehash)**
- Document every major decision and pivot in the Decision Log table:
  - Decision
  - Rationale
  - Alternatives rejected
  - Tradeoff accepted
  - Type (explicit/implicit/emergent)
  - Status (final/tentative/pending)

4) **Requirements Ledger (Verifiable)**
- Record requirements with scope, priority, acceptance criteria, and status.

5) **Critical Context & Insight Evolution**
- Use **[G/C/P/K]** tags to label maturity of each key insight:
  - [G] Genesis (new discovery)
  - [C] Custom (emerging pattern)
  - [P] Product (proven conclusion)
  - [K] Commodity (standard knowledge)
- Include constraints, uncertainty map, and values at stake.

6) **Open Loops**
- List unresolved questions, blockers, pending inputs, and hypotheses to test.

7) **Human Context**
- Document the user’s communication preferences, assumed knowledge, and any sensitive topics.
- If a specific persona (e.g., theological/intelligence framing) is explicitly present in the conversation, capture it. Otherwise mark as N/A.

8) **Forensic Narrative (Optional Depth)**
- Provide an act-based chronology inside the <details> section:
  - Act I: Inception
  - Act II: Exploration
  - Act III: Current State
- Include any load-bearing quotes.

9) **Resumption Handshake**
- End with the receiver command requiring:
  1) Mission (in receiver’s words)
  2) Current status
  3) Immediate next action
- Explicitly instruct the receiver not to rehash decisions already logged.

## Output Requirement

Generate the final artifact as a Markdown document using the Canonical Artifact Template v2.1.

If file export is supported, name it:
`FORENSIC_HANDOVER_[Subject].md`

Finish the artifact with:
**§ TRANSFER READY — Review for accuracy before sharing.**

§ TRANSFER INITIATED — Proceed with forensic reconstruction.