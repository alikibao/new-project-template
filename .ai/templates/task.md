<!-- DO NOT EDIT — TEMPLATE. Copy to .ai/tasks/TASK-<YYYYMMDD>-<slug>.md -->

---
task_id: TASK-<YYYYMMDD>-<NNN>
feature_id: FEAT-<ID>
title: <One-verb, one-object> # e.g., "Add retry to POST /widgets"
owner: <email-or-handle>
priority: P2                  # P0-P3
estimate_minutes: 45
touches_files: 3              # guideline cap
created: <YYYY-MM-DD>
status: active                # active | blocked | done
---

## Goal
<One short paragraph describing the target state once this task is done.>

## Acceptance Criteria
- [ ] <Observable criterion 1>
- [ ] <Observable criterion 2>
- [ ] <Logs/errors/messages defined if relevant>

## Definition of Ready (auto-check)
- [ ] Fits one feature & one user story
- [ ] ≤90 minutes / ≤3 files / ≤150 LOC
- [ ] No hidden dependencies or approvals required
- [ ] Rollback = revert one commit

## Plan
1. <Step 1>
2. <Step 2>
3. …

## File Impact (planned)
- `src/path/fileA.ts`: <change>
- `src/path/fileB.test.ts`: <tests>
- New: `src/path/newFile.ts`: <purpose>

## Test Plan
- Commands: `<pnpm -w test ...>`
- Cases:
  - <Precondition> → <Action> → <Expected>
  - …

## Risks / Edge Cases
- <risk> → <mitigation>

## Checklist (in order)
- [ ] Plan/File Impact/Test Plan set
- [ ] Implement changes
- [ ] Write/Update tests
- [ ] Self-review (style, security, perf)
- [ ] Produce diff + commit + PR text
- [ ] Set `status: done` and fill Done Summary

## Done Summary
- PR: <link or number>
- Notes: <what changed, follow-ups created>
