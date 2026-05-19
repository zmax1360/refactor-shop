# Metrics Rules

Every agent records these at the end of their pass.
Write to the run metrics file: .codeguard/runs/{run-id}/metrics.json

## Required fields — all agents

- run_id: string
- agent: string
- gate: G0 / G1 / G2 / G3 / G4
- status: pass / warn / block / human_required
- retry_count: integer
- duration_mins: integer (estimate)
- token_input_estimate: integer
- token_output_estimate: integer

## Additional fields — by agent

Sofia:
- requirements_extracted: integer (count of REQ-IDs)
- ambiguities_flagged: integer

Marcus:
- files_reviewed: integer
- findings_critical: integer
- findings_high: integer
- findings_medium: integer
- findings_low: integer

Priya:
- legacy_loc_changed: integer (lines in SEARCH blocks)
- new_loc_written: integer (lines in REPLACE blocks)
- first_pass_compile: boolean
- fixes_applied: integer
- fixes_skipped: integer

Dana:
- tests_written: integer
- tests_passed: integer
- tests_failed: integer
- must_requirements_covered: integer
- security_gaps: integer

Eric:
- decision: APPROVE / REQUEST CHANGES / BLOCK
- confidence_score: integer
- human_fix_time_mins: integer (ask user to fill after merge)

## KPI definitions — tracked across runs

token_efficiency: token_input_estimate / legacy_loc_changed
  Target: < 100 tokens per line changed
  If > 200: Priya prompt is pulling too much context

first_pass_compile_rate: track across runs
  Target: > 80% of runs compile on first attempt
  If < 60%: Priya's SEARCH/REPLACE blocks are too large

human_fix_time_mins: filled by developer after merge
  Target: < 15 mins per run
  If > 30 mins: Marcus is missing issues or Priya's fixes are unsafe

security_regression_rate: findings_critical introduced by Priya
  Target: 0
  Any non-zero value: update Marcus's review_focus immediately

## Rules

- Never leave a field as 0 without a reason
- If a value cannot be measured: write -1 and note why
- Do not fabricate token counts — estimate from context size
- human_fix_time_mins is filled by the developer after merge,
  not by the agent
