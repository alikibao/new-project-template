# AI Coding Workflow (Single-Session Loop)

You are stateless. **Always start here.**

## 0) Session Handshake
Read:
- `.ai/project-meta.yaml`
- `.ai/context/current-feature.md`
- `.ai/context/current-task.md`
- `.ai/context/architecture.md`
- `.ai/context/tech-stack.md`
- `prd/mvp.md`

Output a **Context Snapshot** (≤12 bullets) covering: repo layout, feature goal, task scope, constraints, risks, success criteria.
If anything is missing, list **Context Requests** and stop.

## 1) Definition of Ready (DoR)
Confirm the task:
- [ ] Single feature, no cross-epic
- [ ] ≤90 minutes, ≤3 files, ≤150 LOC
- [ ] Explicit acceptance criteria & test plan
- [ ] Rollback = revert one commit

If a box is unchecked, propose the smallest edit to the task to make it ready.

## 2) Plan
Produce:
- File impact list (create/modify/delete)
- 5–10 ordered steps
- Test plan (pre/post + commands)
- Branch & commit strategy (Conventional Commits)

## 3) Implement
- Provide unified diffs/file blocks
- Include migrations/scripts if needed
- Keep reversible and minimal

## 4) Validate
- Exact commands to lint/test
- Sample inputs/outputs
- Self-review checklist (style, tests, security)

## 5) Package
- Patch/diff
- Commit message
- PR description (what/why/how/risk/roll-forward)
- Doc updates if any

## 6) Close the loop
- Mark task **done** (with PR link) in the task file
- Append a note to `prd/completed.md`
- If follow-ups exist, create a new **small** task and update `current-task.md` pointer
