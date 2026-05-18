# CodeGuard Run Artifacts

Each run folder stores the full execution artifacts for a single agent execution.

Example:

runs/run-20260518-001/
├── metadata.json
├── prompt.md
├── diff.patch
├── compile.log
├── test.log
├── metrics.json
└── review.md

Purpose:
- Track prompt effectiveness
- Measure token usage
- Review generated diffs
- Compare prompt versions
- Detect regressions
- Build evaluation benchmarks