# RefactorShop
AI-powered code review and refactoring workflow



# CodeGuard Manual Run Workflow

## Step 1 — Open Release Plan
Identify one implementation task from the release plan.

## Step 2 — Choose Agent
Select the correct CodeGuard agent prompt.

Examples:
- Sofia → requirements analysis
- Marcus → code review
- Priya → refactoring/fixes
- Dana → tests
- Eric → final approval

## Step 3 — Execute In Cursor
Run the selected prompt against the target repository.

## Step 4 — Save Run Artifacts
Store execution artifacts in:

.codeguard/runs/run-XXX/

Artifacts:
- prompt.md
- diff.patch
- compile.log
- test.log
- metrics.json
- review.md

## Step 5 — Review Results
Review:
- compile/test status
- diff quality
- token usage
- regressions
- prompt quality

## Step 6 — Improve System
Only modify prompts/rules based on measurable failures or inefficiencies.