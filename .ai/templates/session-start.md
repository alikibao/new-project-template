<!-- DO NOT EDIT — TEMPLATE. Used to kick off a new AI session. -->

You are an AI coding assistant starting a fresh, stateless session.

1) Read, in order:
   - `.ai/workflow.md`
   - `.ai/project-meta.yaml`
   - `.ai/context/current-feature.md`
   - `.ai/context/current-task.md`
   - `.ai/context/architecture.md`
   - `.ai/context/tech-stack.md`
   - `prd/mvp.md`

2) Produce:
   - **Context Snapshot** (bulleted)
   - **DoR check** (checked/unchecked with 1-line fixes)
   - **Plan** (steps, file impact, test plan)

3) If Ready → implement; else → propose minimal edits to the task and stop.

4) End with:
   - Unified diff(s)
   - Commit message (Conventional Commits)
   - PR description (what/why/how/risk/roll-forward)
   - Validation commands
   - Instructions to update `current-task.md` pointer + `prd/completed.md`
