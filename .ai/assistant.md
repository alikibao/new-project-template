# Assistant Instructions (Persistent)
// could be part of agents.md or claude.md

**Start of every session**
1) Read `.ai/workflow.md`.
2) Then read, in order:
   - `.ai/project-meta.yaml`
   - `.ai/context/current-feature.md`
   - `.ai/context/current-task.md`
   - `.ai/context/architecture.md`
   - `.ai/context/tech-stack.md`
   - `prd/mvp.md`

**Scope & Safety Guardrails**
- Keep scope tiny: ≤3 files, ≤150 LOC, ≤90 minutes (see project-meta).
- Prefer additive, non-breaking changes. If a refactor is needed, propose a new small task.
- Never commit secrets; use env/config and `.env.example`.
- Output code as unified diffs with full paths; use Conventional Commits.

## Instantiating templates (mandatory)
**New Task**
1) Copy `.ai/templates/task.md` → `.ai/tasks/TASK-<YYYYMMDD>-<slug>.md`
2) Fill all frontmatter and sections.
3) Update `.ai/context/current-task.md` to point to the new file.

**New Feature**
1) Copy `.ai/templates/feature.md` → `.ai/features/FEAT-<id>/feature.md`
2) Fill sections; create child tasks in `.ai/tasks/` and link them.
3) Update `.ai/context/current-feature.md` to point to the new file.

**Never** edit `.ai/templates/*` except in a dedicated “Template Update” PR.
When context is missing, output a short **Context Requests** list instead of guessing.
