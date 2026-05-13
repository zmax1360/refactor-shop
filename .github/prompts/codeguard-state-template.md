---
mode: ask
description: CodeGuard shared state document template
commands:
  - name: state
    description: Show current pipeline state for this review
---

This is the template for CodeGuard state files.

State files are created by Sofia at the start of each review
and stored at: .codeguard/CODEGUARD-{YYYYMMDD}-{scope}.md

Each agent reads this file at the start of their pass and
updates ONLY their section at the end of their pass.
No agent touches another agent's section.

═══════════════════════════════════════
PATH CONVENTION — READ THIS FIRST
═══════════════════════════════════════

There are two ways to reference the state file directory
depending on who is doing the referencing:

  AGENT PROMPTS (Sofia, Marcus, Priya, Dana, Eric):
    Reference: .codeguard/
    Reason: agents run from inside repo-scg/ as their
            working directory, so .codeguard/ resolves
            to repo-scg/.codeguard/ at runtime

  ORCHESTRATOR (when created):
    Reference: repo-scg/.codeguard/
    Reason: the orchestrator runs from the repo root
            and must use the full path from there

These two references point to the SAME physical directory:
  repo-scg/.codeguard/

Never store state files at the repo root .codeguard/ —
they always live under repo-scg/.codeguard/.

═══════════════════════════════════════
STATE FILE TEMPLATE
═══════════════════════════════════════

Copy everything below this line into the new state file.
Replace all {placeholders} with real values.

---
# CODEGUARD-{YYYYMMDD}-{SCOPE}

Generated: {timestamp}
PR Scope: {what is being reviewed}
Repository: {repo name}
Branch: {branch name}
Review ID: CODEGUARD-{YYYYMMDD}-{SCOPE}

## Pipeline Status
| Agent  | Gate | Status  | Retries | Notes |
|--------|------|---------|---------|-------|
| Sofia  | G0   | pending | 0       |       |
| Marcus | G1   | pending | 0       |       |
| Priya  | G2   | pending | 0       |       |
| Dana   | G3   | pending | 0       |       |
| Eric   | G4   | pending | 0       |       |

Status values:
  pending          → not started yet
  running          → currently in progress
  pass             → gate passed, next agent can proceed
  warn             → passed with warnings, noted below
  human_required   → paused, waiting for developer decision
  retrying         → agent fixing own output, attempt N of 2
  block            → pipeline stopped, see notes

---

## Requirements Checklist (Sofia — Gate 0)

Gate 0 Status: pending

### MUST IMPLEMENT
| ID | Requirement | Verification | File Hint | Status |
|---|---|---|---|---|
| REQ-001 | (Sofia fills this) | | | pending |

### SHOULD IMPLEMENT
| ID | Requirement | Verification | File Hint | Status |
|---|---|---|---|---|

### NICE TO HAVE
| ID | Requirement | Verification | File Hint | Status |
|---|---|---|---|---|

### Zuul → SCG Mapping
| Zuul Filter | SCG Equivalent | Key Differences |
|---|---|---|

### Ambiguities
(Sofia lists anything unclear here)

---

## Findings (Marcus — Gate 1)

Gate 1 Status: pending

### Requirements Coverage
| REQ-ID | Status | Notes |
|---|---|---|
| REQ-001 | pending | |

### Critical Issues
| ID | File | Line | Issue | Fix |
|---|---|---|---|---|

### High Issues
| ID | File | Line | Issue | Fix |
|---|---|---|---|---|

### Medium Issues
| ID | File | Line | Issue | Fix |
|---|---|---|---|---|

### Low Issues
| ID | File | Line | Issue |
|---|---|---|---|

### Positive Observations
(Marcus fills this)

---

## Fixes Log (Priya — Gate 2)

Gate 2 Status: pending

### Fixes Applied
| Finding | File | Fix Summary |
|---|---|---|

### Fixes Skipped
| Finding | Reason |
|---|---|

### Missing Requirements Flagged
(REQ-XX items not implemented — requires developer decision)

### Compile Check
Command: (not run yet)
Result: pending

---

## Test Results (Dana — Gate 3)

Gate 3 Status: pending

### Tests Written
| Test Class | Method | Covers | Result |
|---|---|---|---|

### Coverage Summary
| REQ-ID | Test | Status |
|---|---|---|

### Test Run
Command: (not run yet)
Result: pending
Confidence: pending

---

## Final Decision (Eric — Gate 4)

Gate 4 Status: pending

Decision: pending
Reason:
Confidence: /100
Date:

---

## Retry Log

(Each agent records retries here)
Format: "{Agent} retry {N} at {timestamp}: {what failed} → {what was tried} → {result}"

---
